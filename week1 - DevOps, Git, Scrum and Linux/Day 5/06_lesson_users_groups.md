# Detailed Guide: Users, Groups, Permissions, and Ownership in Linux


### Lesson Overview

In Linux, managing users, groups, permissions, and ownership is critical for ensuring system security and proper resource allocation. This guide explains how Linux handles these aspects, the underlying concepts, and how to use commands to manage them effectively.

---

### Learning Objectives

By the end of this guide, learners will be able to:

1. Understand the concepts of users, groups, and permissions in Linux.
2. Manage users and groups using command-line tools.
3. Configure file and directory permissions.
4. Change ownership and permissions to enhance system security.
5. Use advanced permission techniques like sticky bits, setuid, and setgid.

---

### 1. Users in Linux

#### Types of Users:
1. Root User:
   - The superuser with full system access.
   - Can perform all administrative tasks (e.g., software installation, user management).
   - The prompt for the root user ends with `#`.

2. Regular Users:
   - Have limited access to system resources.
   - Can access files and directories based on assigned permissions.

3. System Users:
   - Created for running specific services or daemons (e.g., `www-data` for web servers).

#### Commands to Manage Users:
1. Create a User:
   ```bash
   sudo useradd username
   sudo passwd username
   ```

2. Delete a User:
   ```bash
   sudo userdel username
   ```

3. Modify a User:
   ```bash
   sudo usermod -aG groupname username  # Add a user to a group
   sudo usermod -L username            # Lock a user account
   sudo usermod -U username            # Unlock a user account
   ```

4. View User Information:
   ```bash
   whoami  # Shows the current user
   id username  # Displays user ID (UID), group ID (GID), and groups
   ```

---

### 2. Groups in Linux

Groups allow users to share access to files and directories.

#### Types of Groups:
1. Primary Group:
   - Assigned when a user is created.
   - Typically matches the username.

2. Secondary Groups:
   - Additional groups a user can belong to for shared permissions.

#### Commands to Manage Groups:
1. Create a Group:
   ```bash
   sudo groupadd groupname
   ```

2. Add a User to a Group:
   ```bash
   sudo usermod -aG groupname username
   ```

3. Remove a User from a Group:
   ```bash
   sudo gpasswd -d username groupname
   ```

4. View Group Information:
   ```bash
   groups username  # Shows groups a user belongs to
   cat /etc/group   # Lists all groups
   ```

### 4. Ownership in Linux

Each file and directory in Linux has:
1. Owner: The user who owns the file.
2. Group: The group associated with the file.

#### Commands to Manage Ownership:
1. Change Owner (chown):
   ```bash
   sudo chown username file
   ```

2. Change Group (chgrp):
   ```bash
   sudo chgrp groupname file
   ```

3. Change Owner and Group Simultaneously:
   ```bash
   sudo chown username:groupname file
   ```

---

### 5. Advanced Permission Techniques

1. Sticky Bit:
   - Applied to directories to restrict file deletion to the owner.
   - Example:
     ```bash
     chmod +t directory
     ```

2. Setuid (Set User ID):
   - Allows users to execute a file with the permissions of the file owner.
   - Example:
     ```bash
     chmod u+s file
     ```

3. Setgid (Set Group ID):
   - Allows users to execute a file with the permissions of the file’s group.
   - Example:
     ```bash
     chmod g+s file
     ```

---

### 6. Viewing System-Wide User and Group Configurations

1. User Details:
   ```bash
   cat /etc/passwd
   ```

2. Group Details:
   ```bash
   cat /etc/group
   ```

3. Password Policies:
   ```bash
   cat /etc/shadow
   ```
