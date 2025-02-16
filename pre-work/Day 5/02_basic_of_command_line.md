# Introduction to Command Line

## Overview
The command line interface (CLI) is a powerful tool that allows users to interact directly with their operating system. Unlike graphical interfaces, the CLI enables precise and efficient control over system tasks, making it an essential skill for DevOps professionals. This reading material will guide you through the basics of using the command line, helping you build a solid foundation for advanced DevOps workflows.

---

## Learning Outcomes
By completing this material, you will:

1. Understand the purpose and importance of the command line in DevOps.
2. Learn how to navigate the file system using basic commands.
3. Create, view, and edit files from the command line.
4. Manage processes and permissions effectively.
5. Gain exposure to basic scripting for automating repetitive tasks.

---

## Command Line Basics

### 1. What is the Command Line?
- The command line is a text-based interface that allows users to execute commands by typing them.
- It is often referred to as the "shell" and is an alternative to graphical user interfaces (GUIs).
- Popular shells include Bash (Linux), Zsh (macOS), and PowerShell (Windows).

### 2. Accessing the Terminal
- **Windows**: Use "Command Prompt" or "PowerShell."
- **macOS**: Use "Terminal."
- **Linux**: Use your default terminal emulator (e.g., GNOME Terminal).

---

## Navigation Commands

1. `pwd` – Print the working directory.
   - Displays the current directory you are in. For example, if you are in the home directory, it will return something like `/home/username`.
   ```bash
   pwd
   ```

2. `ls` – List files and directories.
   - Shows the contents of a directory. For example, running `ls` in your home directory might list files like `Documents`, `Downloads`, etc.
   ```bash
   ls
   ```

3. `cd` – Change directory.
   - Allows you to navigate to a different directory. For instance, to move into the `Documents` folder, you would use:
   ```bash
   cd Documents
   ```

4. `mkdir` – Create directories.
   - Creates a new folder. For example, to create a folder named `projects` in the current directory:
   ```bash
   mkdir projects
   ```

5. `rmdir` – Remove directories.
   - Deletes an empty directory. For example, if the `projects` folder is empty, you can remove it using:
   ```bash
   rmdir projects
   ```

---

## File Operations

1. `touch` – Create a new file.
   - This command is used to create an empty file. For example, to create a file named `notes.txt`:
   ```bash
   touch notes.txt
   ```

2. `cat` – View file contents.
   - Displays the content of a file. For example, to view the content of `notes.txt`:
   ```bash
   cat notes.txt
   ```

3. `cp` – Copy files or directories.
   - Copies a file or directory to another location. For instance, to copy `notes.txt` to a folder named `backup`:
   ```bash
   cp notes.txt backup/
   ```

4. `mv` – Move or rename files.
   - Moves a file to another location or renames it. For example, to rename `notes.txt` to `new_notes.txt`:
   ```bash
   mv notes.txt new_notes.txt
   ```

5. `rm` – Delete files or directories.
   - Deletes a file or folder. For instance, to delete `notes.txt`:
   ```bash
   rm notes.txt
   ```

---

## Managing Processes and Permissions

1. Viewing Running Processes:
   - `ps`: Lists active processes. For example, running `ps` shows all the processes initiated by the current user.
     ```bash
     ps
     ```
   - `top`: Provides a real-time view of all running processes and their resource usage.
     ```bash
     top
     ```

2. Killing Processes:
   - `kill`: Terminates a process by its ID (PID). For example, if the PID of a process is `1234`, you can stop it using:
     ```bash
     kill 1234
     ```

3. Permissions:
   - View permissions:
     - Use `ls -l` to display file permissions. For example, the output `-rw-r--r--` indicates read and write permissions for the owner, and only read permissions for others.
     ```bash
     ls -l
     ```
   - Change permissions:
     - Use `chmod` to modify permissions. For instance, to grant executable permissions to a file:
     ```bash
     chmod +x script.sh
     ```
   - Change ownership:
     - Use `chown` to change the owner of a file. For example, to assign ownership of `file.txt` to user `alice`:
     ```bash
     chown alice file.txt
     ```

---

## Basic Scripting

### Creating a Script
1. Create a new script file:
   - This creates an empty file where you can write a script. For example:
   ```bash
   touch script.sh
   ```
2. Add commands to the script:
   - Use an editor like `nano` to add commands. For example:
   ```bash
   echo "echo Hello, World!" > script.sh
   ```
3. Make the script executable:
   - Ensures the script can be run directly. For example:
   ```bash
   chmod +x script.sh
   ```
4. Run the script:
   - Execute the script to see the output. For example:
   ```bash
   ./script.sh
   ```

### Example: Automate Directory Cleanup
- This example deletes temporary files from a specified directory:
```bash
#!/bin/bash
# This script deletes temporary files from a directory

echo "Cleaning up..."
rm -rf /path/to/temp/*
echo "Cleanup complete."
```
- Replace `/path/to/temp/` with the path of the directory you want to clean up.

---

## Additional Resources

### Books & Documentation
1. [The Linux Command Line by William Shotts](https://linuxcommand.org/tlcl.php)
2. [GNU Bash Manual](https://www.gnu.org/software/bash/manual/bash.html)

### Interactive Learning Tools
1. [Learn Command Line by Codecademy](https://www.codecademy.com/learn/learn-the-command-line)
2. [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)

### Videos & Tutorials
1. [Linux Command Line Full Course on YouTube](https://www.youtube.com/watch?v=ZtqBQ68cfJc)
2. [Introduction to the Command Line by FreeCodeCamp](https://www.freecodecamp.org/news/the-linux-command-line-beginners-guide/)

---

This material provides the foundational knowledge needed to use the command line effectively in a DevOps environment. Use the additional resources for deeper learning and practice.
