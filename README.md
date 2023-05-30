## Writing a shell in C
A shell is a user interface that provides an interactive way for users to interact with an operating system. 
**It acts as a command interpreter, allowing users to enter commands and execute them to perform various tasks.**

### Shell offers various features and functionalities including:
- **Command execution:** Shells can execute various commands provided by the user, such as launching applications, running scripts, manipulating files and directories, managing processes, and performing system operations.

- **Input/output redirection:** Shells allow users to redirect input and output streams from and to files or other processes. This enables features like piping, where the output of one command can be passed as input to another command.

- **Scripting:** Shells provide a scripting language that allows users to write *scripts*—a series of commands—to automate repetitive tasks, configure system settings, and create more complex operations.

- **Environment management:** Shells manage an environment in which commands are executed. They provide variables to store data, manage paths for executable files, and enable customization through configuration files.

- **Job control:** Shells offer job control features, allowing users to manage multiple processes simultaneously. This includes running processes in the background, suspending and resuming processes, and managing process priorities.

Common examples of shells in the Unix/Linux ecosystem include Bash (Bourne Again SHell), Zsh (Z Shell), Korn Shell (ksh), and C Shell (csh). Each shell may have its own syntax and features, although they generally adhere to.

### Basic lifetime of a shell
Looking at a shell from top down, a shell will do three main things at its lifetime:

1. **Initialize:** In this step, a typical shell would read and execute its configuration files. These change aspects of the shell’s behavior.

1. **Interpret:** Next, the shell reads commands from stdin (which could be interactive, or a file) and executes them.

1. **Terminate:** After its commands are executed, the shell executes any shutdown commands, frees up any memory, and terminates.

Our shell will be so simple that there won’t be any configuration files, and there won’t be any shutdown command. So, we’ll just call the looping function and then terminate. But in terms of architecture, it’s important to keep in mind that the lifetime of the program is more than just looping.

```c
int main(int argc, char **argv)
{
  // Load configuration files, if any.

  // Run command loop.
  d_sh_loop();

  // Perform any shutdown/cleanup.

  return EXIT_SUCCESS;
}
```

In the snippet above, we just loop interpreting commands.

### Basic loop of a shell
We’ve taken care of how the program should start up. Now, for the basic program logic: what does the shell do during its loop? Well, a simple way to handle commands is with three steps:

1. **Read:** Read the command from standard input.
1. **Parse:** Separate the command string into a program and arguments.
1. **Execute:** Run the parsed command.