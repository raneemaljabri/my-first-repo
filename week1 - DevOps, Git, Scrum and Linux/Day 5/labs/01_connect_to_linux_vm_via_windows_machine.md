# Guided Lab: Connecting to an Azure Linux Virtual Machine via PuTTY and PowerShell

## Overview  
After provisioning a Linux Virtual Machine (VM) on Azure, you need to establish a Secure Shell (SSH) connection to manage and configure the VM. Azure provides multiple ways to connect to a Linux VM, including PuTTY (a popular SSH client for Windows) and PowerShell. This guided lab will walk you through setting up PuTTY and using PowerShell to connect to your Azure Linux VM.

By the end of this lab, you will have successfully connected to a Linux VM using both PuTTY and PowerShell, enabling remote administration and management.



## Pre-requisites  
Before starting this lab, ensure you have:  
1. An active Azure subscription with access to the Azure Portal.  
2. A Linux Virtual Machine already deployed in Azure.  
3. The public IP address of your Linux VM.  
4. SSH Key Pair (if used for authentication) or a username-password for the VM.  
5. PuTTY installed on your system (for Windows users).  
6. PowerShell installed (Pre-installed on Windows, available for macOS and Linux).  



## Learning Objectives  
By the end of this lab, you will be able to:  
1. Retrieve the public IP address of an Azure Linux Virtual Machine.  
2. Connect to the Linux VM using PuTTY (for Windows users).  
3. Use PowerShell to connect to the Linux VM via SSH.  
4. Perform basic administrative tasks on the Linux VM after connecting.  



## Step-by-Step Guide  

### Step 1: Retrieve the Public IP Address of the Linux VM  
1. Log in to the [Azure Portal](https://portal.azure.com).  
2. Navigate to Virtual Machines and select your Linux VM.  
3. On the VM Overview page, locate the Public IP Address under the Networking section.  
4. Copy the Public IP Address (e.g., `20.90.220.45`) for use in the next steps.  



## Method 1: Connecting via PuTTY (Windows Users)  

### Step 2: Install and Configure PuTTY  
1. Download PuTTY from [PuTTY Official Website](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).  
2. Install PuTTY by following the on-screen instructions.  
3. Open PuTTY from your Start Menu.  

### Step 3: Connect to Linux VM using PuTTY  
1. In PuTTY, enter the Public IP Address of your VM in the Host Name (or IP address) field.  
2. Set Port to 22 (default SSH port).  
3. Ensure Connection Type is set to SSH.  
4. Click Open to initiate the connection.  

### Step 4: Login to the Linux VM  
1. If prompted with a security alert, click Yes to accept the SSH key.  
2. Enter the username (e.g., `azureuser`) when prompted.  
3. If using password authentication, enter the password and press Enter.  
4. If using SSH Key Authentication, PuTTY will automatically use the private key associated with the key pair.  

### Step 5: Verify Connection and Perform Basic Commands  
Once logged in, verify that you are connected by running:  
```bash
whoami
```
This should return your Linux username. You can also check system information:  
```bash
uname -a
```
To list files in your home directory:  
```bash
ls -al
```



## Method 2: Connecting via PowerShell (Windows, macOS, Linux)  

### Step 6: Open PowerShell  
1. On Windows, press `Win + X`, then select PowerShell or Terminal.  
2. On macOS and Linux, open Terminal.  

### Step 7: Connect to the Linux VM via SSH in PowerShell  
Run the following command in PowerShell, replacing `<public-ip>` with your VM’s public IP address:  
```powershell
ssh azureuser@<public-ip>
```
For example:  
```powershell
ssh azureuser@20.90.220.45
```

If using SSH Key Authentication, specify your private key file:  
```powershell
ssh -i "C:\path\to\private-key.pem" azureuser@<public-ip>
```

### Step 8: Verify Connection and Run Basic Commands  
Once connected, verify the system information:  
```bash
uname -a
```
Check disk space usage:  
```bash
df -h
```
List running processes:  
```bash
ps aux
```



## Optional: Transferring Files to the Linux VM using SCP (PowerShell)  
If you need to transfer files to your Linux VM, use scp (Secure Copy Protocol):  

To copy a file from your computer to the VM:  
```powershell
scp C:\Users\YourUser\example.txt azureuser@<public-ip>:~/
```
To copy a file from the VM to your computer:  
```powershell
scp azureuser@<public-ip>:~/example.txt C:\Users\YourUser\
```


## Suggested Reading  
📖 [Azure Virtual Machines Documentation](https://learn.microsoft.com/en-us/azure/virtual-machines/)  
📖 [How to SSH into an Azure Linux VM](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys)  
📖 [PuTTY SSH Key Authentication](https://www.ssh.com/academy/ssh/putty)