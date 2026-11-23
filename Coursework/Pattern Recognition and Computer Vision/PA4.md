This is **PA4: build a Vision Transformer (ViT) from scratch and use it to classify CIFAR-10**. It's 100 points split into two parts, and it continues from PA3: same dataset, same loading code, with one small change to normalization.

The Big Picture:
A CNN slides filters over an image. A ViT does something different. It chops the image into small square patches, treats each patch like a "word," and feeds that sequence of patch-words into a Transformer, the same architecture used for language. The Transformer lets every patch "look at" every other patch through attention, so the model can relate distant parts of the image directly.

You'll build this in three stages:

1. **Part 1:** the generic Transformer pieces (attention, MLP, encoder layers, positional encoding).
2. **Part 2, first half:** the image-specific parts (patches to tokens, the full ViT). You then train it from scratch.
3. **Part 2, second half:** load weights from a ViT pretrained on ImageNet, adapt them to CIFAR's tiny 32×32 images, fine-tune, and explain the results in writing.

Every task comes with a sanity-check cell that tests your implementation against an exact reference. So you'll always know whether you got it right before moving on.

### Part 1: Transformer building blocks (40 pts)

**Task 1.1, Multi-head attention (16 pts, the biggest single task).** Each token has a C-dimensional vector. You project the tokens three ways, into queries (Q), keys (K), and values (V), using learned linear layers with bias. Each token's query is compared against every token's key. The scores are scaled by 1/√d and softmaxed, and the result is used to take a weighted average of the values.

"Multi-head" means the C channels are split into h groups of d = C/h channels. Each group runs its own independent attention, and then the results are concatenated and passed through an output projection.

The catch is **no for loops over heads**. You have to reshape the (B, L, C) tensor so the heads become their own dimension, (B, h, L, d), and then do all the heads in one batched matrix multiply. The exact ordering also matters: head i must use channels i·d to (i+1)·d. The sanity check compares your output to PyTorch's built-in `nn.MultiheadAttention` to within 1e-5, so the order of reshape vs. transpose has to be exactly right.

**Task 1.2, Feedforward network (4 pts).** A two-layer MLP applied to each token independently: linear, then GELU, then dropout, then linear. The hidden size is usually 4× the input size. This is the simplest task.

**Task 1.3, Pre-norm encoder cell (8 pts).** One Transformer "layer" combines the two pieces above with residual connections:

- x ← x + Dropout(Attention(LayerNorm(x)))
- x ← x + Dropout(FFN(LayerNorm(x)))

"Pre-norm" means the LayerNorm goes _before_ each sublayer, on its input. The original 2017 Transformer was post-norm, with the norm applied after the residual addition. Pre-norm is what modern ViTs use, and it trains more stably.

**Task 1.4, Encoder stack (4 pts).** Stack N cells in sequence using `nn.ModuleList`, then apply one final LayerNorm at the end.

**Task 1.5, Sinusoidal positional encoding (8 pts).** Attention by itself has no notion of order. If you shuffled the patches, it would produce the same set of outputs. So you add a position signal to each token. For each position and each pair of dimensions (2i, 2i+1), you use sin and cos at a frequency that gets lower as i grows. This gives every position a unique "fingerprint."

There are three requirements here: no loops, it must work when d is odd (careful with the cos half!), and you use `self.max_len` as the base instead of a hardcoded 10000.

### Part 2: ViT on CIFAR-10 (60 pts)

**Task 2.1, Patch embedding (4 pts).** This turns a (B, 3, 32, 32) image into a sequence of tokens. The trick is a single `Conv2d` whose kernel size and stride both equal the patch size P. Because the stride matches the kernel, the windows don't overlap. Each output position is then just a linear projection of one patch.

With P = 4 you get an 8×8 grid of 64 patches. You then flatten and transpose to (B, 64, D). The order must be **row-major**: left to right, then top to bottom.

**Task 2.2, Full VisionTransformer (6 pts).** Wire everything together in this order:

1. Patch embedding
2. Positional encoding
3. Dropout
4. Encoder stack
5. Average over all tokens (global average pooling)
6. Linear head that outputs 10 class scores

**Task 2.3, Overfitting check (3 pts).** Before spending GPU time on the full dataset, prove your model _can_ learn. You train a tiny ViT on just 250 images from 5 classes and need >90% training accuracy.

Your only job is choosing the model's hyperparameters. It must have fewer than 71K parameters, output 5 classes (not 10), and use dropout = 0. If accuracy stays near 20%, which is chance level for 5 classes, something is broken in Part 1.

**Task 2.4, Train from scratch (12 pts).** Now train on all 49K training images for only 3 epochs. You need **>56% test accuracy** with **under 1.5M parameters**.

You tune four things: learning rate, `embed_dim`, `num_heads`, and `num_cells`. Batch size, dropout, and `ff_dim` are fixed. The hint says to change one number at a time and to prioritize depth and width.

**Task 2.5, ViT with a CLS token (8 pts).** The pretrained model you're about to load was built slightly differently, so your model has to match its structure. There are two changes:

- A learnable **CLS token** is prepended at position 0, so you have 65 tokens instead of 64.
- The positional encoding is **learned** rather than sinusoidal, and it covers 65 positions.

The `__init__` is given, and you only write `forward`. One detail to watch: you still average only the 64 patch tokens and throw away the CLS output. The CLS token is kept only because the pretrained weights expect something at position 0.

**Task 2.6, Interpolate the positional embedding (10 pts).** The pretrained model saw 224×224 images with 16×16 patches, which is a 14×14 grid, plus CLS, giving 197 positions. Your model has an 8×8 grid, so its learned position vectors don't fit.

The fix is to treat the 196 grid vectors as a tiny 14×14 "image" with D channels and resize it to 8×8 with bicubic interpolation. The CLS vector is pulled out first and put back unchanged afterward.

The sanity check tests three things. First, that the CLS slot is untouched. Second, that you didn't scramble rows and columns, which is where most bugs will come from: reshape vs. permute order. Third, that you used `antialias=True`.

**Provided, not graded: kernel resizing.** The pretrained patch kernel is 16×16 but you need 4×4. You can't simply interpolate it, because that doesn't preserve the dot products the kernel computes. The provided code uses a pseudo-inverse method from FlexiViT. You don't implement it, but it's worth understanding for the written answers.

**Task 2.7, Fine-tune with patch 4 vs. 16, plus written answers (10 pts).** You run two experiments. The patch-4 model gets 64 tokens and needs **>83%**. The patch-16 model keeps the original kernel but gets only a 2×2 = 4-token grid on a 32×32 image.

You then answer four questions about why patch-4 wins:

1. Tokens per image and how much of the image each token covers, compared with pretraining.
2. How much positional information can survive shrinking 14×14 down to 2×2 vs. 8×8.
3. Whether patch-16 fails to fit the training data or fails to generalize (compare train vs. val accuracy).
4. Computation per image despite similar parameter counts.

**Task 2.8, Skip the positional interpolation (7 pts).** Same as patch-4, but with a random positional embedding instead of the interpolated pretrained one. You compare the accuracy and explain what the pretrained embedding was giving you for free.