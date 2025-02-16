# Using the Linux Shell

## Overview

Before graphical interfaces with icons and windows dominated computer screens, interacting with computers meant typing commands. On UNIX systems—the foundation of Linux—the program responsible for interpreting and executing these commands was known as the shell.

No matter which Linux distribution you use, the shell is always available and serves as a critical tool for managing and interacting with the system. It allows you to:

- Create and run executable scripts
- Launch programs and applications
- Navigate and manipulate the file system
- Compile source code into executable programs
- Manage and configure the computer

While the shell may not seem as intuitive as modern graphical user interfaces (GUIs), it is widely regarded by Linux experts as far more powerful and versatile. Mastering the shell opens the door to advanced system control and automation, making it an essential skill for any Linux user.

## Lesson Objectives

By the end of this lesson, learners will be able to:

1. Understand the Role of the Shell Prompt

    - Define the shell prompt and explain its significance in Linux.

    - Recognize the components of a typical shell prompt (e.g., user, hostname, current directory, and prompt symbol).

2. Navigate and Manage the Shell Environment

    - Execute basic commands to navigate the file system (pwd, ls, cd).

    - View and manipulate files using commands like cat, less, head, and tail.

3. Execute Commands Effectively

    - Understand the structure of Linux commands, including options and arguments.
    - Run multiple commands sequentially using semicolons (;).

4. Customize the Shell Prompt

    - Modify the appearance of the shell prompt using the PS1 variable.
    - Make shell prompt customizations permanent by editing the .bashrc file.

5. Leverage Advanced Shell Features

    - Use tab completion to speed up command execution.
    - Utilize the command history feature for efficiency.
    - Redirect command output to files and use pipes to connect commands.
    - Manage background and foreground jobs effectively.

6. Perform Common Tasks Using the Shell Prompt

    - Practice file and directory management commands (touch, mkdir, rm, cp, mv).
    - Retrieve system information using commands like whoami, uname -a, and df -h.
    - Understand and manage file permissions with chmod and chown.


## Explanation 

### Using the Shell Prompt:

The shell prompt is the text interface provided by the shell where users can type and execute commands. It acts as the starting point for interacting with the Linux operating system, allowing users to run programs, manage files, and configure the system.

The shell prompt typically looks like this:

`user@hostname:~$`

- user: Your username.
- hostname: The name of the computer.
- `~`: The current working directory (in this case, your home directory).
- `$` or `#`: Indicates the user type:
    - `$`: Regular user.
    - `#`: Root (superuser) with elevated privileges.

### Navigating the Shell Prompt

**Basic Commands:**

- `pwd`: Displays the current working directory.
- `ls`: Lists files and directories in the current location.
- `cd [directory]`: Changes the working directory.

**Viewing Files:**

- `cat filename`: Displays the contents of a file.
- `less filename`: Allows scrolling through file content.
- `head filename`: Shows the first 10 lines of a file.
- `tail filename`: Shows the last 10 lines of a file.

Executing Commands:
**1. Running Simple Commands:**

    Type a command and press Enter:
```
echo "Hello, World!"

```

- The shell executes the command and displays the output.

**2. Command Syntax: Most Linux commands follow this structure:**

```
command [options] [arguments]
```

- command: The action to perform.
- options: Modify the behavior of the command (e.g., -l for long listing in ls).
- arguments: Additional inputs, such as file or directory names.

Example:

```
ls -l /home/user
```

**3. Running Multiple Commands:**

Use a semicolon (;) to execute multiple commands sequentially:

```
pwd; ls; echo "Done!"

```

### Customizing the Shell Prompt

You can modify the shell prompt to suit your preferences by changing the PS1 variable.

Example:

```
PS1="\u@\h:\w\$ "
```

- `\u`: Username.
- `\h`: Hostname.
- `\w`: Current working directory.

To make changes permanent, edit the .bashrc file in your home directory:

```
nano ~/.bashrc
```

### Tips for Using the Shell Prompt

1. Tab Completion:

- Press Tab to auto-complete file names, commands, or directory paths.

2. Command History:

- Use the up and down arrow keys to navigate through previously entered commands.

- View the history with:

```
history
```


3. Redirection and Pipes:

- Redirect output to a file:

```
ls > output.txt
```

- Pipe the output of one command into another:

```
ls | grep "keyword"
```

- Background and Foreground Jobs:

Run a command in the background with `&`:

```
sleep 10 &
```

Bring it to the foreground with `fg`.

### Common Commands to Practice:

**1. File Management:**

- `touch file.txt`: Creates an empty file.
- `rm file.txt`: Deletes a file.
- `mkdir folder`: Creates a new directory.
- `cp source destination`: Copies files.
- `mv source destination`: Moves or renames files.

**2. System Information:**

- `whoami`: Displays the current user.
- `uname -a`: Displays system information.
- `df -h`: Shows disk usage.
- `top`: Monitors system processes.

**3. Permissions:**

- `chmod`: Changes file permissions.

- `chown`: Changes file ownership.


## Suggested Reading

[The Linux Command line for beginners](https://ubuntu.com/tutorials/command-line-for-beginners)

[50 Most Popular Linux and Terminal Commands](https://www.youtube.com/watch?v=ZtqBQ68cfJc&ab_channel=freeCodeCamp.org)