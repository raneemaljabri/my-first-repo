# Lesson: Linux Directory Structure



## Overview

Linux follows a well-organized directory structure that helps in organizing system files, configurations, applications, and user data. Understanding the Linux directory structure is crucial for navigating and managing files efficiently.

This lesson provides a detailed breakdown of the Linux directory hierarchy, the purpose of each directory, and common commands to navigate the filesystem.



## Learning Objectives

By the end of this lesson, learners will:
1. Understand the Linux Filesystem Hierarchy Standard (FHS).
2. Learn the purpose of each major directory in Linux.
3. Use basic Linux commands to navigate and manage directories.



## Topics Covered

1. Understanding the Linux Filesystem Hierarchy Standard (FHS)
2. Overview of the Root (`/`) Directory
3. Major Linux Directories and Their Functions



## 1. Understanding the Linux Filesystem Hierarchy Standard (FHS)

The Filesystem Hierarchy Standard (FHS) defines the directory structure and directory contents in Linux distributions. It ensures a consistent directory layout across different Linux systems.

Key Principles of FHS:
- Everything is organized under the root (`/`) directory.
- System files, configuration files, and user files have designated locations.
- Separation of system files and user files helps in security and maintainability.



## 2. Overview of the Root (`/`) Directory

The root directory (`/`) is the base of the Linux filesystem. All files and directories stem from here.

Important Characteristics:
- Represented as a single forward slash (`/`).
- Contains system-critical files and subdirectories.
- Requires superuser (root) permissions for modifications.



## 3. Major Linux Directories and Their Functions

| Directory   | Purpose |
|---|---|
| `/bin`         | Essential binary executables (e.g., `ls`, `cat`, `cp`). |
| `/boot`        | Bootloader files (e.g., `vmlinuz` kernel, `grub`). |
| `/dev`         | Device files (e.g., `sda` for hard drives, `tty` for terminals). |
| `/etc`         | System-wide configuration files (e.g., `/etc/passwd`, `/etc/hosts`). |
| `/home`        | User home directories (e.g., `/home/user`). |
| `/lib`         | Essential shared libraries required by binaries. |
| `/media`       | Mount points for removable media (e.g., USB, CDs). |
| `/mnt`         | Temporary mount points for external filesystems. |
| `/opt`         | Optional application software (e.g., third-party packages). |
| `/proc`        | Virtual filesystem providing system information (e.g., CPU, memory). |
| `/root`        | Home directory for the root user. |
| `/run`         | Runtime data, including process and system info. |
| `/sbin`        | System administration binaries (e.g., `fdisk`, `reboot`). |
| `/srv`         | Data for system services (e.g., web servers). |
| `/sys`         | Virtual filesystem for kernel and device management. |
| `/tmp`         | Temporary files; cleared on reboot. |
| `/usr`         | User binaries, libraries, and documentation. |
| `/var`         | Variable files (e.g., logs, mail, databases). |



## Suggested Reading and Resources

1. [Linux File System Explained](https://tldp.org/LDP/Linux-Filesystem-Hierarchy/html/)
2. [The Linux Documentation Project](https://www.tldp.org/)
3. YouTube Video: [Linux File System Hierarchy Explained](https://www.youtube.com/watch?v=KyZqSWWKmHQ)