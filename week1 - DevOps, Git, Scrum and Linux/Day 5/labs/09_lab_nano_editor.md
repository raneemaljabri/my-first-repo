## Guided Lab: Working with the Nano Editor in Linux



## Learning Objectives

By the end of this lab, students will:

1. Understand the basics of the `nano` editor and its interface.
2. Open, edit, save, and close files using `nano`.
3. Perform basic text navigation, insertion, and deletion.
4. Use advanced features like search, replace, and keyboard shortcuts.



## Lab Challenge:  
"Mastering Nano Basics"  
Your task is to create and modify a text file using the `nano` editor, following the guided steps.



## Steps to Complete the Lab

### Step 1: Open the Nano Editor
1. Open the terminal.
2. Use the `nano` command to create or open a file named `example.txt`:
   ```bash
   nano example.txt
   ```



### Step 2: Insert Text
1. Begin typing the following text:
   ```
   Nano Editor Lab
   This is a guided exercise to learn nano basics.
   Text editing in nano is simple and efficient.
   ```
2. Save the file:
   - Press `Ctrl + O` (Write Out).
   - Press `Enter` to confirm the filename.



### Step 3: Navigate the Text
1. Use the following keys to move the cursor:
   - Arrow Keys: Move up, down, left, and right.
   - Ctrl + A: Jump to the beginning of the current line.
   - Ctrl + E: Jump to the end of the current line.
   - Ctrl + V: Move down one screen.
   - Ctrl + Y: Move up one screen.



### Step 4: Delete Text
1. Delete the word "simple" from the third line:
   - Place the cursor on the word and press `Ctrl + K` to cut the line.
   - Re-type the line without "simple."
2. Delete the entire second line:
   - Place the cursor anywhere on the line and press `Ctrl + K`.



### Step 5: Undo and Redo Changes
1. Undo the last change:
   - Press `Alt + U`.
2. Redo the undone change:
   - Press `Alt + E`.



### Step 6: Search and Replace Text
1. Search for the word "nano":
   - Press `Ctrl + W` (Where Is).
   - Type `nano` and press `Enter`.
2. Replace the word "nano" with "Nano Editor":
   - Press `Ctrl + \` (Search and Replace).
   - Type `nano` as the search term, press `Enter`.
   - Type `Nano Editor` as the replacement, press `Enter`.
   - Confirm each occurrence or press `A` to replace all.



### Step 7: Copy and Paste Text
1. Copy the first line:
   - Move the cursor to the line and press `Alt + 6`.
2. Paste the copied line below the second line:
   - Move the cursor to the desired location and press `Ctrl + U`.



### Step 8: Save and Exit
1. Save the file:
   - Press `Ctrl + O`.
   - Press `Enter` to confirm.
2. Exit nano:
   - Press `Ctrl + X`.



## Lab Completion Check

Ensure the following:
1. The file `example.txt` exists and contains the edited content.
2. You can perform all the tasks: inserting text, navigating, deleting, undoing, searching, replacing, copying, pasting, and exiting.



## Additional Challenge
1. Open a new file named `challenge.txt` and type a short paragraph about your favorite Linux command.
2. Save the file and replace all occurrences of a chosen word with another word.
3. Add a new line at the beginning of the file and save it again.