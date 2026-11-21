Think of sandbox as a seperate controlled space where you let a program do things while limiting what it can affect. 

Let’s build that idea with a few examples.

### 1. Imagine trying a script on your laptop

Someone gives you a program and says:

> “Run this. It will organize your files.”

If you run it normally, it might have permission to change or delete your actual files.

Instead, imagine putting it inside a controlled space containing only three sample files:

Sample photo
Sample document
Sample video

You let the program organize those files. It cannot access your real photos or documents because you haven’t given it access.

**That controlled space is a sandbox.**

The important part is the **restriction**: the program gets access only to what you allow.

Real Usecases of Sandbox that developers actually use:

| Example                              | How developers use it                                               | What’s restricted or separated                                                                                    |
| ------------------------------------ | ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Browser JavaScript**               | Run website code in Chrome or Safari.                               | Website code generally can’t freely read your laptop’s files or run system commands.                              |
| **Stripe test mode**                 | Test checkout using test card numbers and simulate failed payments. | Test transactions don’t charge real money.                                                                        |
| **Docker containers**                | Run an app, database, or unfamiliar tool in a separate environment. | Processes and files are isolated to a degree; access depends on settings such as mounted folders and permissions. |
| **Android Emulator / iOS Simulator** | Test mobile apps without using a physical phone.                    | Apps run in a separate simulated device environment, with platform restrictions.                                  |
| **An online code runner**            | Try a Python snippet or submit a coding problem.                    | Execution typically has limits on time, memory, file access, and network access.                                  |
| **A restricted VM**                  | Test software or scripts in a disposable operating system.          | Access to the host computer and network can be limited.                                                           |


Now, Is a Virtual Machine and a Sandbox the same?

**Not exactly. A VM can be used as a sandbox, but they mean different things.****

- A **[[virtual machine]] (VM)** is a software-based computer with its own operating system. For example, running Ubuntu inside your Mac.
- A **sandbox** is a restricted environment that limits what software can access or affect. It doesn’t need an entire operating system.
  
  A **VM is a virtual computer**. A **sandbox is a controlled space**. You can use a virtual computer to create that controlled space.

For example, on your Mac:

1. You create an Ubuntu VM.
2. You keep your Mac’s folders disconnected from it.
3. You put sample files inside Ubuntu.
4. You run the unfamiliar program there.
5. When finished, you delete or reset the VM.

**The VM is being used as a sandbox.** Its configuration determines what the program can reach; isolation isn’t an absolute guarantee.

But the payment test mode and browser restrictions above are also sandboxes, even though you didn’t create a VM.

Sandbox Vs [[Blackbox]]

| Feature                  | Black box                                                        | Sandbox                                                                  |
| ------------------------ | ---------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Main idea                | You observe inputs and outputs without inspecting the internals. | A controlled environment that limits what software can access or affect. |
| Focus                    | How you view or test a system.                                   | Where software runs and its restrictions.                                |
| Main question            | What output does this input produce?                             | What can this program access or change?                                  |
| Example                  | Testing a login page without reading its code.                   | Running a script with access only to sample files.                       |
| Does it restrict access? | No.                                                              | Yes, depending on its configuration.                                     |
| Relationship to a VM     | A VM can be treated as a black box.                              | A VM can be used to create a sandbox.                                    |


