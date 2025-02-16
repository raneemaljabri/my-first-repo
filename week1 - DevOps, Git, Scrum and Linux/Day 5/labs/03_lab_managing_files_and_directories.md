# Guided Lab: Managing Files and Directories in Linux

## Learning Objectives:
By the end of this lab, students will be able to:
1. Understand and use basic file and directory management commands.
2. Create, delete, copy, and move files and directories.
3. Navigate the Linux filesystem efficiently.
4. Set and modify file permissions.



## Lab Challenge: 
"File and Directory Explorer"  
Your task is to create a directory structure, manage files within it, and configure permissions based on a real-world scenario.



## Steps to Complete the Challenge

### Step 1: Create a Directory Structure
1. Open a terminal.
2. Create a directory named `project_files` in your home directory:
   ```bash
   mkdir ~/project_files
   ```
3. Navigate into the `project_files` directory:
   ```bash
   cd ~/project_files
   ```
4. Inside `project_files`, create the following subdirectories:
   - `docs`
   - `scripts`
   - `data`
   ```bash
   mkdir docs scripts data
   ```



### Step 2: Manage Files
1. Create three empty files in the `docs` directory:
   ```bash
   touch docs/readme.txt docs/changelog.txt docs/license.txt
   ```
2. Copy the `readme.txt` file into the `scripts` directory:
   ```bash
   cp docs/readme.txt scripts/
   ```
3. Move the `changelog.txt` file to the `data` directory:
   ```bash
   mv docs/changelog.txt data/
   ```



### Step 3: Modify and Display File Content
1. Add the text "Project Documentation" to `readme.txt`:
   ```bash
   echo "Project Documentation" > docs/readme.txt
   ```
2. Append the text "Version 1.0" to `license.txt`:
   ```bash
   echo "Version 1.0" >> docs/license.txt
   ```
3. Display the content of `readme.txt`:
   ```bash
   cat docs/readme.txt
   ```



### Step 4: Set Permissions
1. Grant read and write permissions to the owner and read-only permissions to others for all files in the `docs` directory:
   ```bash
   chmod 644 docs/*
   ```
2. Make the `scripts` directory executable for the owner, group, and others:
   ```bash
   chmod 755 scripts
   ```
3. Verify permissions using the `ls -l` command:
   ```bash
   ls -l docs scripts
   ```



### Step 5: Clean Up
1. Delete the `data` directory along with its contents:
   ```bash
   rm -r data
   ```
2. Rename the `scripts` directory to `utilities`:
   ```bash
   mv scripts utilities
   ```



## Lab Completion Check
At the end of the lab, ensure the following:
1. The `project_files` directory has the structure:
   ```
   project_files/
   ├── docs/
   │   ├── readme.txt
   │   ├── license.txt
   └── utilities/
       └── readme.txt
   ```
2. Permissions are correctly applied to files and directories:
   - Files in `docs`: `rw-r--r--`
   - Directory `utilities`: `rwxr-xr-x`
    (Verify directory permissions using the `ls -ld utilities` command)


## Additional Challenge:
1. Compress the `project_files` directory into a `.tar.gz` archive:
   ```bash
   tar -czvf project_files.tar.gz .
   ```
   or run the following command from the parent directory:

   ```bash
   tar -czvf project_files.tar.gz project_files
   ```
2. Extract the archive to verify its contents:
   ```bash
   tar -xzvf project_files.tar.gz
   ```

Let me know if you'd like to add more challenges or tailor the lab further!