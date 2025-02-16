## Challenge Lab: Editing a File Using Your Favorite Editor (vi or nano)



## Learning Objectives

By the end of this lab, students will:

- Demonstrate their proficiency in using either `vi` or `nano` for file editing.
- Apply basic and advanced editing techniques to modify a text file.
- Practice file navigation, content modification, and saving changes.



## Scenario:

You are tasked with editing a configuration file for a project. Use your favorite text editor (`vi` or `nano`) to perform the required modifications. Your task is to ensure the file is properly formatted and contains the specified content.



## Requirements

1. File Setup:
   - Create a file named `project_config.txt` in your home directory.
   - Populate it with the following content:
     ```
     # Project Configuration
     Name: MyProject
     Version: 1.0
     Author: [Your Name]
     Description: This is a sample configuration file.
     ```

2. Editing Tasks:
   - Replace `[Your Name]` with your actual name.
   - Add a new line at the end of the file with the text:
     ```
     License: MIT
     ```
   - Delete the line starting with `Description`.

3. Formatting Tasks:
   - Indent the `Name`, `Version`, and `Author` lines with two spaces at the beginning.
   - Ensure there are no trailing spaces at the end of any line.

4. Additional Requirements:
   - Search for the word `Project` and verify its occurrences.
   - Undo any accidental changes you make during the editing process.

5. Save and Verify:
   - Save the file with the changes.
   - Display the contents of the file to verify the formatting and modifications:
     ```bash
     cat project_config.txt
     ```



## Notes:

- Students can use either `vi` or `nano` to complete this lab.
- No step-by-step instructions are provided to encourage independent problem-solving.
- Test your edits to ensure they meet the requirements.

Good luck! Let me know if you'd like to add more complexity or variations!