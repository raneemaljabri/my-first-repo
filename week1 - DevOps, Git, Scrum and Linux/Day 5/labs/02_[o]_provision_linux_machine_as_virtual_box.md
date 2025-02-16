## Lab: Deploying a Linux Virtual Machine on VirtualBox on a Windows Machine



## Lab Overview

In this lab, you will learn how to deploy a Linux virtual machine (VM) using Oracle VirtualBox on a Windows machine. The lab walks you through downloading VirtualBox, obtaining a Linux distribution ISO, configuring a virtual machine, and installing Linux.


## Learning Objectives

By completing this lab, learners will:
1. Install Oracle VirtualBox on a Windows machine.
2. Download and configure a Linux ISO for a virtual machine.
3. Set up and install Linux on the virtual machine.
4. Understand basic VM settings for performance optimization.



## Pre-Requisites

1. A Windows machine with at least:
   - 8 GB RAM (minimum 4 GB for Linux VM).
   - 50 GB free disk space.
   - Virtualization enabled in BIOS (e.g., Intel VT-x or AMD-V).
2. An active internet connection to download VirtualBox and a Linux ISO file.



## Steps



### 1. Install Oracle VirtualBox

1. Download VirtualBox:
   - Visit the [VirtualBox Official Website](https://www.virtualbox.org/).
   - Navigate to the Downloads section and select the installer for Windows.

2. Install VirtualBox:
   - Run the installer and follow the prompts.
   - Choose default options unless specific changes are required.
   - Allow the installer to install the VirtualBox network drivers.

3. Launch VirtualBox:
   - After installation, open VirtualBox to ensure it works correctly.



### 2. Download a Linux ISO

1. Choose a Linux Distribution:
   - Popular options include Ubuntu, CentOS, Fedora, and Debian.
   - For this lab, we will use Ubuntu Desktop.

2. Download the ISO File:
   - Visit the [Ubuntu Downloads Page](https://ubuntu.com/download/desktop).
   - Download the latest version of the Ubuntu Desktop ISO.



### 3. Create a New Virtual Machine

1. Open VirtualBox:
   - Launch VirtualBox and click on New to create a new virtual machine.

2. Configure the VM Settings:
   - Name: Enter a name (e.g., `Ubuntu VM`).
   - Machine Folder: Keep the default location or specify a custom folder.
   - Type: Select `Linux`.
   - Version: Choose the appropriate version (e.g., `Ubuntu (64-bit)`).

3. Allocate Memory (RAM):
   - Assign at least 2 GB (2048 MB) for Ubuntu Desktop.
   - Recommended: 4 GB for better performance.

4. Create a Virtual Hard Disk:
   - Select Create a virtual hard disk now and click Create.
   - Choose VDI (VirtualBox Disk Image) as the file type.
   - Select Dynamically allocated for storage.
   - Specify disk size (minimum 20 GB, recommended 50 GB).



### 4. Attach the Linux ISO

1. Access VM Settings:
   - Select the newly created VM in VirtualBox.
   - Click Settings > Storage.

2. Add the ISO File:
   - Under the Controller: IDE, click the empty disk icon.
   - Click the CD icon on the right side and choose Choose a disk file.
   - Browse to the location of the downloaded Linux ISO and select it.

3. Enable Boot from ISO:
   - Ensure the attached ISO is set to boot the VM.



### 5. Start the Virtual Machine

1. Launch the VM:
   - Click Start to boot the VM.

2. Boot from ISO:
   - The VM will boot into the Linux installer from the ISO file.

3. Follow Installation Steps:
   - Language: Choose your preferred language and click Continue.
   - Keyboard Layout: Select your keyboard layout and click Continue.
   - Installation Type: Choose Erase disk and install Ubuntu (this applies to the virtual disk only).
   - Username and Password: Create a username and password for the Linux system.
   - Complete the installation process by following the on-screen prompts.

4. Reboot the VM:
   - After installation, reboot the VM.
   - Remove the ISO file by going to Devices > Optical Drives > Remove disk from virtual drive in the VirtualBox menu.



### 6. Configure Virtual Machine Settings

1. Optimize Resources:
   - CPU: Allocate 2 or more CPUs (Settings > System > Processor).
   - Video Memory: Increase to 128 MB (Settings > Display > Screen).

2. Enable Shared Clipboard:
   - Go to Settings > General > Advanced and enable Bidirectional clipboard sharing.

3. Install Guest Additions:
   - Start the VM and log in to Linux.
   - Go to Devices > Insert Guest Additions CD Image.
   - Follow the prompts to install VirtualBox Guest Additions for enhanced performance and features.



### 7. Verify the Installation

1. Check System Information:
   - Open a terminal and run:
     ```bash
     uname -a
     ```
   - Verify the Linux kernel version and architecture.

2. Test Internet Connectivity:
   - Open a browser in the VM and navigate to a website.

3. Update the System:
   - Open a terminal and update the system packages:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```



## Completion Checklist

- [ ] VirtualBox installed and configured.
- [ ] Linux ISO downloaded and attached to the VM.
- [ ] Linux installed and running in the VM.
- [ ] Virtual Machine optimized for performance.



## Troubleshooting Tips

1. Virtualization Not Enabled:
   - Enable virtualization (Intel VT-x or AMD-V) in the BIOS/UEFI settings.

2. Slow Performance:
   - Allocate more RAM or CPUs in the VM settings.
   - Ensure Guest Additions are installed.

3. Networking Issues:
   - Check network settings in VirtualBox (use NAT for internet access).



## Suggested Reading and Resources

1. [VirtualBox Documentation](https://www.virtualbox.org/manual/)
2. [Ubuntu Desktop Installation Guide](https://ubuntu.com/tutorials/install-ubuntu-desktop)
