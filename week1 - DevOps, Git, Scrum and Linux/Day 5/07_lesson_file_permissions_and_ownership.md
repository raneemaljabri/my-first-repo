# Detailed Guide: Files, Permissions, and Ownership in Linux

## Lesson Overview

In Linux, managing file permissions and ownership is crucial to maintaining security and control. This guide explores how Linux handles files, assigns permissions, and manages ownership. It also covers the commands and techniques needed to configure and manage these aspects effectively.

## Learning Objectives

By the end of this guide, learners will be able to:

1. Understand the Linux file system structure and the types of files in Linux.
2. Explain the concept of file permissions and their components.
3. Manage file permissions using command-line tools.
4. Configure file ownership for users and groups.
5. Utilize advanced techniques like sticky bits, setuid, and setgid to enhance security.



## 1. Files in Linux

### Types of Files:
1. Regular Files (`-`):
   - Contain data, such as text, scripts, or programs.
   - Example: `/etc/passwd`, `file.txt`.

2. Directories (`d`):
   - Containers that hold other files or directories.
   - Example: `/home`, `/var/log`.

3. Symbolic Links (`l`):
   - Shortcuts pointing to another file or directory.
   - Example: `/var/www -> /home/user/website`.

4. Special Files:
   - Block Devices (`b`): Represent devices like hard drives.
   - Character Devices (`c`): Represent devices like keyboards.
   - Sockets (`s`): Used for inter-process communication.
   - Pipes (`p`): Allow data flow between processes.



## 2. File Permissions

Permissions control what actions users and groups can perform on files and directories.

### Permission Types:
1. Read (`r`): View the content of a file or list a directory’s contents.
2. Write (`w`): Modify the content of a file or create/delete files in a directory.
3. Execute (`x`): Run a file as a program or access a directory.

### Permission Representation:
Permissions are represented using a string:
```bash
-rwxr-xr--
```

- `-`: Indicates the file type (e.g., `d` for directory).
- `rwx`: Owner’s permissions.
- `r-x`: Group’s permissions.
- `r--`: Other (world) permissions.

### Numeric Representation of Permissions:
Permissions can also be represented numerically:
- Read (4)
- Write (2)
- Execute (1)

For example:
- `7` (4+2+1): Full permission (read, write, execute).
- `5` (4+1): Read and execute.
- `0`: No permission.



## 3. Managing File Permissions

### Viewing Permissions:
Use `ls` with the `-l` option to list file permissions:
```bash
ls -l
```

### Changing Permissions (chmod):
1. Symbolic Mode:
   ```bash
   chmod u+rwx file  # Add read, write, and execute for the owner
   chmod g-rwx file  # Remove read, write, and execute for the group
   chmod o+r file    # Add read permission for others
   ```

2. Numeric Mode:
   ```bash
   chmod 755 file
   ```
   - Owner: Read, write, execute (`7`).
   - Group: Read, execute (`5`).
   - Others: Read, execute (`5`).



## 4. Ownership in Linux

Every file and directory in Linux has two types of ownership:
1. Owner: The user who owns the file.
2. Group: The group associated with the file.

### Viewing Ownership:
```bash
ls -l
```
Output example:
```bash
-rw-r--r-- 1 alice developers 1024 Jan 21 12:00 file.txt
```
- Owner: `alice`
- Group: `developers`



### Changing Ownership:

1. Change Owner (chown):
   ```bash
   sudo chown newowner file
   ```

2. Change Group (chgrp):
   ```bash
   sudo chgrp newgroup file
   ```

3. Change Both Owner and Group:
   ```bash
   sudo chown newowner:newgroup file
   ```



## 5. Special Permissions

### Sticky Bit:
- Applied to directories to restrict file deletion to the owner.
- Commonly used in directories like `/tmp`.
- Example:
  ```bash
  chmod +t directory
  ```

### Setuid (Set User ID):
- Allows users to execute a file with the permissions of the file owner.
- Commonly used for system commands like `passwd`.
- Example:
  ```bash
  chmod u+s file
  ```

### Setgid (Set Group ID):
- Allows users to execute a file with the permissions of the file’s group.
- Example:
  ```bash
  chmod g+s file
  ```



## 6. Default Permissions: umask

The `umask` command sets the default permissions for newly created files and directories.

1. View Current umask:
   ```bash
   umask
   ```

2. Set a New umask:
   ```bash
   umask 022
   ```
   - Ensures new files are created with permissions `755`.



## 7. Practical Examples

1. Restrict File Access:
   ```bash
   chmod 600 file.txt
   ```
   - Only the owner can read and write.

2. Share a Directory:
   ```bash
   chmod 770 shared_directory
   chown alice:team shared_directory
   ```
   - Allows only the owner and team group members to access it.

3. Secure Temporary Directory:
   ```bash
   chmod +t /tmp
   ```
   - Prevents users from deleting files they don’t own.
