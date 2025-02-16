### Lab: Provisioning a Linux Machine Using WSL on Windows

### Lab Overview

Windows Subsystem for Linux (WSL) allows you to run a Linux environment directly on Windows without the need for a virtual machine or dual boot. This lab will guide you through installing WSL, provisioning a Linux distribution, and configuring the Linux environment for development or administrative tasks.



### Learning Objectives

By the end of this lab, learners will:
1. Install and enable WSL on a Windows machine.
2. Provision a Linux distribution using WSL.
3. Configure the WSL environment for productive usage.
4. Use WSL to run Linux commands and applications.



### Pre-Requisites

1. A Windows 10 (version 1903 or higher) or Windows 11 machine.
2. Administrative privileges on the Windows system.
3. An active internet connection.



### Steps



#### 1. Enable Windows Subsystem for Linux (WSL)

1. Open PowerShell as Administrator:
   - Press `Win + X` and select Windows PowerShell (Admin).

2. Enable WSL:
   - Run the following command to enable the WSL feature:
     ```powershell
     dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
     ```

3. Enable Virtual Machine Platform:
   - Run the following command to enable the Virtual Machine Platform (required for WSL 2):
     ```powershell
     dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
     ```

4. Restart Your System:
   - Restart the machine to apply the changes.



#### 2. Install WSL 2

1. Set WSL 2 as the Default Version:
   - After restarting, open PowerShell as Administrator and run:
     ```powershell
     wsl --set-default-version 2
     ```

2. Check WSL Version Compatibility:
   - Verify if your system supports WSL 2 by running:
     ```powershell
     wsl --list --verbose
     ```



#### 3. Install a Linux Distribution

1. Open Microsoft Store:
   - Search for and open the Microsoft Store from the Start menu.

2. Search for Linux Distributions:
   - Type "Linux" in the search bar and select a distribution (e.g., Ubuntu, Debian, Kali Linux).

3. Install the Chosen Distribution:
   - Click Get to install your preferred Linux distribution.

4. Launch the Linux Distribution:
   - Once installed, launch the distribution from the Start menu.
   - On the first launch, the distribution will initialize, and you'll be prompted to:
     - Create a new Linux username.
     - Set a password.



#### 4. Configure the Linux Environment

1. Update System Packages:
   - Run the following commands to update the package manager:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```

2. Install Essential Tools:
   - Install common tools for development or administration:
     ```bash
     sudo apt install -y curl git build-essential
     ```

3. Set Up SSH (Optional):
   - Install OpenSSH if required:
     ```bash
     sudo apt install -y openssh-server
     ```

4. Verify the Setup:
   - Check the Linux version:
     ```bash
     lsb_release -a
     ```



#### 5. Access Linux Files in Windows

1. Locate WSL Files:
   - Navigate to your Linux file system using File Explorer:
     - Open `\\wsl$` in the address bar to access your WSL instance.

2. Work Across Systems:
   - Copy files between your Windows and Linux environments seamlessly.



#### 6. Use WSL for Development

1. Install a Code Editor:
   - Install Visual Studio Code and its Remote - WSL extension from the Extensions Marketplace.

2. Open a Project in WSL:
   - Launch Visual Studio Code, and open a folder directly from your WSL instance.

3. Run Applications:
   - Test running a simple Node.js application or Python script within WSL.



### Completion Checklist

- [ ] WSL enabled and configured.
- [ ] Linux distribution installed and initialized.
- [ ] System updated and essential tools installed.
- [ ] File sharing between Windows and WSL verified.
- [ ] Linux environment ready for development or administration tasks.



### Troubleshooting Tips

1. Error: WSL Not Enabled:
   - Ensure both WSL and Virtual Machine Platform features are enabled in PowerShell.

2. Slow Performance:
   - Ensure that your Windows installation is up to date and that virtualization is enabled in the BIOS/UEFI settings.

3. Networking Issues:
   - Use the Windows network interface if you encounter connectivity issues within WSL.

4. Cannot Access Linux Files:
   - Ensure WSL is running, and verify the path `\\wsl$` in File Explorer.



### Suggested Reading and Resources

1. [WSL Official Documentation](https://learn.microsoft.com/en-us/windows/wsl/)
2. [Install WSL on Windows 10/11](https://learn.microsoft.com/en-us/windows/wsl/install)
3. YouTube Video: "Getting Started with WSL 2"  
   [![Getting Started with WSL 2](https://img.youtube.com/vi/uhRWMGBjlO8/0.jpg)](https://www.youtube.com/watch?v=uhRWMGBjlO8)
