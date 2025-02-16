# Editing Files in Command Line

## Overview
Editing files directly from the command line is a valuable skill for DevOps professionals. It allows for quick configuration changes, script edits, and troubleshooting without requiring a graphical interface. This material introduces essential tools and commands to edit files efficiently in the command line environment.

---

## Learning Outcomes
By completing this material, you will:

1. Understand the importance of file editing in the command line.
2. Learn how to use common text editors like `nano`, `vim`, and `sed`.
3. Gain the ability to modify files, search and replace text, and save changes.
4. Automate simple file editing tasks using command-line tools.

---

## Common File Editors

### 1. Nano Editor
`nano` is a beginner-friendly text editor available on most Linux and macOS systems. It is easy to use for basic file editing tasks.

**Opening a File:**
- To open a file in `nano`, use the following command:
  ```bash
  nano filename.txt
  ```
- If the file does not exist, `nano` will create a new one.

**Editing the File:**
- Use the arrow keys to navigate through the file.
- Type to add or modify text.

**Saving and Exiting:**
- Press `Ctrl + O` to save the file. You will be prompted to confirm the filename.
- Press `Ctrl + X` to exit the editor.

**Shortcut Summary:**
- `Ctrl + W`: Search for text in the file.
- `Ctrl + K`: Cut the current line.
- `Ctrl + U`: Paste the cut line.

### 2. Vim Editor
`vim` is a powerful and versatile text editor often used by advanced users. It has two modes: **Insert** (for editing) and **Command** (for executing commands).

**Opening a File:**
- To open a file in `vim`, use:
  ```bash
  vim filename.txt
  ```
- If the file does not exist, `vim` will create a new one.

**Basic Commands:**
- Press `i` to enter **Insert Mode** and start editing text.
- Press `Esc` to return to **Command Mode**.

**Saving and Exiting:**
- In **Command Mode**, type `:w` to save changes.
- Type `:q` to exit. To save and exit in one step, use `:wq`.
- Use `:q!` to quit without saving changes.

**Shortcut Summary:**
- `/search-term`: Search for a term in the file.
- `dd`: Delete the current line.
- `u`: Undo the last change.
- `p`: Paste copied or deleted text.

### 3. Sed (Stream Editor)
`sed` is a command-line tool for performing text transformations on files. It is useful for automating file edits without opening an editor.

**Basic Syntax:**
- `sed 's/search/replace/' filename` replaces the first occurrence of `search` with `replace` in each line of the file.
  ```bash
  sed 's/old-text/new-text/' filename.txt
  ```

**Editing In-Place:**
- Use the `-i` option to edit files in place:
  ```bash
  sed -i 's/old-text/new-text/' filename.txt
  ```

**Example:**
- To replace all occurrences of "error" with "warning" in a log file:
  ```bash
  sed -i 's/error/warning/g' logfile.txt
  ```

---

## Practical Examples

### Example 1: Using Nano for Configuration Files
- Open a configuration file (e.g., `config.yaml`):
  ```bash
  nano config.yaml
  ```
- Modify the desired lines.
- Save and exit with `Ctrl + O`, `Enter`, and `Ctrl + X`.

### Example 2: Using Vim for Script Edits
- Open a shell script:
  ```bash
  vim script.sh
  ```
- Press `i` to edit the script, make your changes, and press `Esc`.
- Save and exit with `:wq`.

### Example 3: Automating Edits with Sed
- Replace "localhost" with "127.0.0.1" in a configuration file:
  ```bash
  sed -i 's/localhost/127.0.0.1/' config.cfg
  ```
- Verify the changes using:
  ```bash
  cat config.cfg
  ```

---

## Additional Resources

### Books & Documentation
1. [Vim Adventures](https://vim-adventures.com/) – A fun way to learn Vim.
2. [GNU Nano Manual](https://www.nano-editor.org/docs.php)
3. [Sed User Guide](https://www.gnu.org/software/sed/manual/sed.html)

### Interactive Learning Tools
1. [OpenVim: Vim Tutorial](https://www.openvim.com/)
2. [Learn Nano Basics](https://linuxize.com/post/how-to-use-nano-text-editor/)
3. [Sed Cheat Sheet](https://devhints.io/sed)

### Videos & Tutorials
1. [Vim Basics for Beginners](https://www.youtube.com/watch?v=IiwGbcd8S7I)
2. [How to Use Nano Text Editor](https://www.youtube.com/watch?v=JcJzlyzD5dA)
3. [Sed Tutorial for Beginners](https://www.youtube.com/watch?v=_iWRdKEAn0c)

---

This material provides essential skills for editing files in the command line, helping DevOps professionals quickly adapt to various scenarios. Use the additional resources for deeper learning and practice.
