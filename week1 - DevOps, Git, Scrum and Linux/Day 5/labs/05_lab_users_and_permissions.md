# Guided Lab - Users Permissions and Ownershiop

## Learning Objectives:

By the end of this lab, students will be able to:
1. Create and manage user accounts.
2. Assign users to groups.
3. Modify and check file permissions.
4. Apply the principle of least privilege using permissions.



## Lab Challenge:  
"User and Permission Mastery"  
Your task is to create users, assign them to groups, and manage permissions for specific files and directories.



## Steps to Complete the Challenge

### Step 1: Create User Accounts
1. Open a terminal and log in as the root user or use `sudo`.
2. Create two users: `alice` and `bob`:
   ```bash
   sudo useradd alice
   sudo useradd bob
   ```
3. Set passwords for both users:
   ```bash
   sudo passwd alice
   sudo passwd bob
   ```



### Step 2: Create Groups and Assign Users
1. Create a group named `project_team`:
   ```bash
   sudo groupadd project_team
   ```
2. Add `alice` and `bob` to the `project_team` group:
   ```bash
   sudo usermod -aG project_team alice
   sudo usermod -aG project_team bob
   ```



### Step 3: Create a Shared Directory
1. Create a directory named `team_files` in `/home`:
   ```bash
   sudo mkdir /home/team_files
   ```
2. Change the group ownership of the directory to `project_team`:
   ```bash
   sudo chown :project_team /home/team_files
   ```
3. Grant group members read, write, and execute permissions on the directory:
   ```bash
   sudo chmod 770 /home/team_files
   ```



### Step 4: Set Permissions for a File
1. Create a file named `project_notes.txt` inside the `team_files` directory:
   ```bash
   sudo touch /home/team_files/project_notes.txt
   ```
2. Set the file’s ownership to `alice` and its group to `project_team`:
   ```bash
   sudo chown alice:project_team /home/team_files/project_notes.txt
   ```
3. Set the following permissions for the file:
   - Owner: Read and write.
   - Group: Read and write.
   - Others: No access.
   ```bash
   sudo chmod 660 /home/team_files/project_notes.txt
   ```



### Step 5: Verify Permissions
1. Switch to `alice` and check access:
   ```bash
   su - alice
   cd /home/team_files
   ls -l
   ```
2. Switch to `bob` and confirm access to the file:
   ```bash
   su - bob
   cd /home/team_files
   cat project_notes.txt
   ```
3. Attempt to access the file as a user outside the `project_team` group (e.g., `root` or another user) and observe the results.



### Step 6: Enforce Special Permissions
1. Enable the setgid bit on the `team_files` directory so that files created in the directory inherit the group ownership of `project_team`:
   ```bash
   sudo chmod g+s /home/team_files
   ```
2. Verify the setgid bit is set:
   ```bash
   ls -ld /home/team_files
   ```



## Lab Completion Check
Ensure the following:
1. The `team_files` directory:
   - Belongs to the `project_team` group.
   - Allows only `alice` and `bob` to access and modify its content.
   - Applies the setgid bit to inherit group ownership.
2. The `project_notes.txt` file:
   - Has the correct permissions (`660`).
   - Is accessible by `alice` and `bob` but not others.

