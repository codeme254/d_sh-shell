## Writing a shell in C
A shell is a user interface that provides an interactive way for users to interact with an operating system. 
**It acts as a command interpreter, allowing users to enter commands and execute them to perform various tasks.**

### Shell offers various features and functionalities including:
- **Command execution:** Shells can execute various commands provided by the user, such as launching applications, running scripts, manipulating files and directories, managing processes, and performing system operations.

- **Input/output redirection:** Shells allow users to redirect input and output streams from and to files or other processes. This enables features like piping, where the output of one command can be passed as input to another command.

- **Scripting:** Shells provide a scripting language that allows users to write *scripts*—a series of commands—to automate repetitive tasks, configure system settings, and create more complex operations.

- **Environment management:** Shells manage an environment in which commands are executed. They provide variables to store data, manage paths for executable files, and enable customization through configuration files.

- **Job control:** Shells offer job control features, allowing users to manage multiple processes simultaneously. This includes running processes in the background, suspending and resuming processes, and managing process priorities.

Common examples of shells in the Unix/Linux ecosystem include Bash (Bourne Again SHell), Zsh (Z Shell), Korn Shell (ksh), and C Shell (csh). Each shell may have its own syntax and features, although they generally adhere to