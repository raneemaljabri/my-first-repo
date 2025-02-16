## Challenge Lab: Managing Files and Directories



## Learning Objectives

By the end of this lab, students will:

- Demonstrate their ability to manage files and directories in Linux.
- Create and manipulate directories and files based on specific requirements.
- Apply file operations like moving, copying, and modifying content.
- Set and verify appropriate permissions and ownership.



## Scenario:

Your organization is preparing a directory structure to store data for an upcoming event. Your task is to create and organize directories and files, populate them with relevant content, and apply the appropriate permissions and ownership.



## Requirements

1. Directory Structure:
   - Create a main directory named `event_files`.
   - Inside `event_files`, create the following subdirectories:
     - `registration`
     - `reports`
     - `backup`

2. File Management:
   - Create the following files:
     - A file named `participants.txt` in the `registration` directory.
     - A file named `summary.csv` in the `reports` directory.
     - A file named `data_backup.tar.gz` in the `backup` directory.
   - Move the `participants.txt` file from the `registration` directory to the `reports` directory.
   - Rename the `data_backup.tar.gz` file to `event_backup.tar.gz`.

3. Content Manipulation:
   - Add the names of five participants to the `participants.txt` file.
   - Append the line "Event Summary Report" to the `summary.csv` file.
   - Extract the contents of the `event_backup.tar.gz` file into the `backup` directory.

4. Permissions and Ownership:
   - Grant the `reports` directory read and write permissions for the owner and group, but no permissions for others.
   - Set the `backup` directory to read-only for all users.
   - Ensure all files and directories in `event_files` are owned by the user `event_admin` and group `event_team`.

5. Verification:
   - Display the final directory structure of `event_files` along with their permissions and ownership.
   - Show the contents of `participants.txt` and `summary.csv` to verify the correct content has been added.



## Notes:

- Students must document the commands they used for each step.
- Test the commands to ensure they meet the stated requirements.
- There are no step-by-step solutions; students should troubleshoot independently and apply their knowledge.

Good luck! Let me know if you'd like to add more complexity or adjust the scenario.