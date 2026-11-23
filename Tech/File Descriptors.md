
---
aliases:
  - FD
  - FDs
  - file descriptors
  - Unix file descriptor
  - Linux file descriptor
---


A **file descriptor** is a small non-negative integer (0, 1, 2, 3, ...) that a process uses to refer to something it has opened: a file, a pipe, a network socket, a terminal, or a device.

When you open a file, the OS does the real work of finding it , checking permissions and setting up its bookkeeping, and then hands back to you just the number. From then on, you use that number for every operation: read from 3, write to 3, close 3

Example Code:

#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main(void) {
    int fd = open("notes.txt", O_RDONLY);   // ask the OS to open the file
    if (fd < 0) { perror("open"); return 1; }
    printf("got file descriptor %d\n", fd);

    char buf[100];
    ssize_t n = read(fd, buf, sizeof buf);  // read using the number
    write(1, buf, n);                       // write to fd 1 (the screen)

    close(fd);                              // give the ticket back
}

Why 3?
because 0,1,2 were aldready taken

The three standard file descriptors:
Every process starts with three descriptors aldready open:

| FD  | Name                    | Connected to |
| --- | ----------------------- | ------------ |
| 0   | standard input(stdin)   | keyboard     |
| 1   | standard output(stdout) | terminal     |
| 2   | standard error(stderr)  | terminal     |
When you call `printf`, it eventually calls `write(1, ...)`. When `scanf` reads input, it calls `read(0, ...)`. That's why `write(1, buf, n)` in the example printed to the screen.

The OS always assigns the **lowest unused number**. Since 0, 1, 2 are taken, the first file you open gets 3, the next gets 4, and so on. If you close 3 and open another file, it gets 3 again. This rule turns out to be very useful, as you'll see with redirection.

### What's behind the number

The integer is just an index. Behind it sit three layers of kernel data structures:

**1. Per-process file descriptor table.** Each process has its own table. Entry 3 holds a pointer to an entry in the next layer. This is why fd 3 in one process and fd 3 in another can mean completely different files.

**2. System-wide open file table.** Each entry here represents one "open" of a file and stores:

- the **current offset** (where the next read or write happens)
- the **mode** (read-only, write-only, read/write, append)
- a reference count
- a pointer to the file itself

**3. The inode (or vnode).** The actual file on disk: its size, permissions, owner, and where its data blocks are.

Process A fd table                                     Open file table                             Inodes
  0 → terminal
  1 → terminal
  2 → terminal
  3 ────────────────→  [offset 120, read]  ────→  notes.txt
  4 ────────────────→  [offset 0, write]   ────→  log.txt

### Everything is a file"

This is why file descriptors are so central in Unix and Linux. The same small set of operations (`read`, `write`, `close`) works on almost everything:

| Thing                  | How you get a descriptor     |
| ---------------------- | ---------------------------- |
| Regular file           | `open("data.txt", ...)`      |
| Pipe between processes | `pipe(fds)`                  |
| Network connection     | `socket(...)`, `accept(...)` |
| Terminal               | already fds 0, 1, 2          |
| Device                 | `open("/dev/random", ...)`   |

Now, lets see how the shell does redirection:

When you type : ls > out.txt

The shell roughly does this:
pid_ 