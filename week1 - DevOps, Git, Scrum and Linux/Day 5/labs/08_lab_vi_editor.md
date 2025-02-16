## Guided Lab: Working with the vi Editor in Linux

---

## Learning Objectives

By the end of this lab, students will:

1. Understand the basics of the `vi` editor and its modes.
2. Open, edit, save, and close files using `vi`.
3. Perform text navigation, insertion, and deletion.
4. Search, replace, and undo changes in `vi`.

---

## Lab Challenge:  
"Mastering vi Basics"  
Your task is to create and modify a text file using the `vi` editor, following the guided steps.

---

## Steps to Complete the Lab

### Step 1: Open the vi Editor
1. Open the terminal.
2. Use the `vi` command to create or open a file named `sample.txt`:
   ```bash
   vi sample.txt
   ```

---

### Step 2: Understand vi Modes
The `vi` editor operates in three modes:
- Normal Mode: Used for navigation, searching, and editing commands.
- Insert Mode: Allows text insertion.
- Command Mode: Used to execute commands like saving or quitting.

---

### Step 3: Insert Text
1. Switch to Insert Mode:
   - Press `i` to enter Insert Mode.
2. Add the following text to the file:
   ```
   Welcome to the vi editor lab.
   This is a guided exercise.
   Let's learn the basics of text editing.
   ```
3. Exit Insert Mode:
   - Press `Esc`.

---

### Step 4: Navigate the Text
1. Use the following commands to move the cursor:
   - `h`: Move left.
   - `l`: Move right.
   - `k`: Move up.
   - `j`: Move down.

2. Navigate to the beginning of the second line:
   - Press `2G`.

3. Jump to the end of the last line:
   - Press `G`.

---

### Step 5: Delete Text
1. Delete the word "guided" on the second line:
   - Move the cursor to the word and press `dw`.

2. Delete the entire third line:
   - Move the cursor to the third line and press `dd`.

---

### Step 6: Undo and Redo Changes
1. Undo the last deletion:
   - Press `u`.

2. Redo the undone deletion:
   - Press `Ctrl + r`.

---

### Step 7: Save and Quit
1. Save the changes and exit the file:
   - Press `Esc` to enter Command Mode.
   - Type `:wq` and press `Enter`.

---

### Step 8: Search and Replace Text
1. Reopen the file:
   ```bash
   vi sample.txt
   ```

2. Search for the word "basics":
   - Press `/` followed by the word `basics`, and press `Enter`.

3. Replace the word "basics" with "fundamentals":
   - Enter Command Mode by pressing `Esc`.
   - Type:
     ```bash
     :%s/basics/fundamentals/g
     ```
   - Press `Enter`.

---

### Step 9: Copy and Paste Lines
1. Copy the first line:
   - Move the cursor to the first line and press `yy`.
2. Paste the copied line below the second line:
   - Move the cursor to the second line and press `p`.

---

### Step 10: Exit Without Saving
1. Make some changes to the file.
2. Exit without saving:
   - Press `Esc` to enter Command Mode.
   - Type `:q!` and press `Enter`.

---

## Lab Completion Check

Ensure the following:
1. The file `sample.txt` exists and contains the edited content.
2. You can perform all the tasks: inserting text, navigating, deleting, undoing, searching, replacing, and exiting the file.

---

## Additional Challenge
1. Open a new file named `challenge.txt` and type a short paragraph about your favorite Linux command.
2. Save the file and replace all occurrences of a chosen word with another word.
3. Exit and verify the file’s content.