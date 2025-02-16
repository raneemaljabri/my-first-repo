## Detailed Guide: Using the `vi` Editor in Linux



## Lesson Overview

The `vi` editor is a powerful and widely used text editor in Linux. Known for its efficiency and versatility, `vi` is often the default editor found on most Linux systems. This guide will introduce the `vi` editor, its modes, commands, and advanced features to help you become proficient in using it for text editing tasks.



## Learning Objectives

By the end of this guide, learners will be able to:

1. Understand the structure and purpose of the `vi` editor.
2. Navigate through the `vi` editor's modes.
3. Perform basic text editing tasks like creating, modifying, and saving files.
4. Utilize advanced commands for efficient editing.
5. Customize the `vi` environment for better usability.



## 1. What is the `vi` Editor?

The `vi` editor (short for "visual editor") is a text editor available on almost all Unix-like operating systems. It is lightweight and operates entirely in the terminal, making it ideal for editing configuration files, scripts, and plain text files.



## 2. Starting the `vi` Editor

### Opening a File:
1. To open a file:
   ```bash
   vi filename
   ```
   - If the file does not exist, `vi` creates a new file with the specified name.

2. Open a file in read-only mode:
   ```bash
   vi -R filename
   ```

### Exiting the `vi` Editor:
- Save and exit:
  ```bash
  :wq
  ```
- Exit without saving:
  ```bash
  :q!
  ```
- Save without exiting:
  ```bash
  :w
  ```



## 3. Modes in `vi`

The `vi` editor operates in three main modes:

### 1. Command Mode:
- This is the default mode when you open a file.
- Used for navigation, deletion, copying, and other operations.
- To enter command mode from insert mode, press `Esc`.

### 2. Insert Mode:
- Allows you to insert and edit text.
- To enter insert mode, press:
  - `i` to insert at the current cursor position.
  - `a` to append after the current position.
  - `o` to open a new line below the cursor.
- Exit insert mode by pressing `Esc`.

### 3. Last Line Mode:
- Used for saving, exiting, and other administrative tasks.
- Accessed by pressing `:` in command mode.



## 4. Basic Navigation Commands

| Command | Description                             |
|--- |--|
| `h`     | Move cursor left                        |
| `l`     | Move cursor right                       |
| `j`     | Move cursor down                        |
| `k`     | Move cursor up                          |
| `0`     | Move to the beginning of the current line |
| `^`     | Move to the first non-blank character   |
| `$`     | Move to the end of the current line     |
| `w`     | Jump to the start of the next word      |
| `b`     | Jump to the beginning of the previous word |
| `G`     | Move to the last line of the file       |
| `gg`    | Move to the first line of the file      |
| `Ctrl + d` | Scroll down half a screen            |
| `Ctrl + u` | Scroll up half a screen              |



## 5. Editing Commands

### Insert and Delete:
| Command | Description                                 |
|---|---|
| `i`     | Insert before the cursor                   |
| `a`     | Insert after the cursor                    |
| `o`     | Open a new line below                      |
| `x`     | Delete the character under the cursor      |
| `dd`    | Delete the current line                    |
| `dw`    | Delete from the cursor to the end of the word |
| `d$`    | Delete from the cursor to the end of the line |
| `u`     | Undo the last action                       |
| `Ctrl + r` | Redo the last undone action             |

### Copy, Cut, and Paste:
| Command | Description                                 |
|---|---|
| `yy`    | Copy the current line                      |
| `yw`    | Copy from the cursor to the end of the word |
| `p`     | Paste after the cursor                     |
| `P`     | Paste before the cursor                    |



## 6. Search and Replace

### Search:
| Command       | Description                            |
|---|---|
| `/pattern`    | Search forward for a pattern          |
| `?pattern`    | Search backward for a pattern         |
| `n`           | Repeat the search in the same direction |
| `N`           | Repeat the search in the opposite direction |

### Replace:
| Command                          | Description                                   |
|---|---|
| `:s/old/new`                     | Replace the first occurrence of "old" with "new" on the current line |
| `:s/old/new/g`                   | Replace all occurrences of "old" with "new" on the current line |
| `:%s/old/new/g`                  | Replace all occurrences in the file          |
| `:%s/old/new/gc`                 | Replace all occurrences in the file with confirmation |



## 7. Advanced Features

### Visual Mode:
- Used for selecting text:
  - `v`: Enter visual mode to select characters.
  - `V`: Select entire lines.
  - `Ctrl + v`: Enter block visual mode.

### Split Windows:
- Open a file in a new split window:
  ```bash
  :split filename
  ```
- Navigate between splits:
  - `Ctrl + w` followed by arrow keys.

### Markers:
- Mark a position in the file:
  ```bash
  ma  # Marks the current position as 'a'
  ```
- Jump to a marker:
  ```bash
  'a
  ```

### Line Numbers:
- Enable line numbers:
  ```bash
  :set number
  ```
- Disable line numbers:
  ```bash
  :set nonumber
  ```



## 8. Customizing `vi`

### Modify `.vimrc` File:
To customize `vi` (or `vim`), edit the `.vimrc` file in your home directory:
```bash
nano ~/.vimrc
```

### Examples of Customizations:
1. Enable syntax highlighting:
   ```vim
   syntax on
   ```
2. Enable line numbers:
   ```vim
   set number
   ```
3. Set tabs to 4 spaces:
   ```vim
   set tabstop=4
   set shiftwidth=4
   set expandtab
   ```



## 9. Practical Examples

1. Create a File:
   ```bash
   vi myfile.txt
   ```
   - Enter insert mode with `i`, type your text, and save with `:wq`.

2. Search and Replace:
   - Replace "error" with "warning" throughout the file:
     ```bash
     :%s/error/warning/g
     ```

3. Delete Multiple Lines:
   - Delete 5 lines:
     ```bash
     5dd
     ```



## 10. Troubleshooting and Exiting

### Recover from Freeze:
- Press `Esc` repeatedly to return to command mode.

### Force Exit Without Saving:
```bash
:q!
```
