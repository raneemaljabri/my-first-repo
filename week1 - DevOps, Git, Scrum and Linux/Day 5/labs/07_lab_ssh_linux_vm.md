# Guided Lab: Configuring SSH Access Between Two Linux Virtual Machines Using Public-Private Key Pairs



## Learning Objectives:

By the end of this lab, students will:

1. Understand the concept of SSH key-based authentication.
2. Generate an SSH key pair.
3. Configure key-based authentication for secure remote access between Linux virtual machines.
4. Test the SSH connection using the key pair.



## Lab Setup:

- Machine 1 (Client): The machine from which the SSH connection will be initiated.
- Machine 2 (Server): The machine to which the SSH connection will be made.

Ensure both machines are accessible and SSH is installed and running on both.



## Steps to Complete the Lab

### Step 1: Verify SSH Installation
1. Check if SSH is installed on both machines:
   ```bash
   ssh -V
   ```
   If SSH is not installed, use the following commands:
   - Ubuntu/Debian:
     ```bash
     sudo apt update
     sudo apt install openssh-server openssh-client -y
     ```
   - RHEL/CentOS:
     ```bash
     sudo yum install openssh-server openssh-clients -y
     ```
2. Start and enable the SSH service on the server:
   ```bash
   sudo systemctl start sshd
   sudo systemctl enable sshd
   ```



### Step 2: Generate an SSH Key Pair on the Client
1. On Machine 1 (Client), generate an SSH key pair:
   ```bash
   ssh-keygen -t rsa -b 2048
   ```
   - Press `Enter` to save the key in the default location (`~/.ssh/id_rsa`).
   - Optionally, set a passphrase for added security or press `Enter` to leave it empty.

2. Verify the generated key pair:
   - Private key: `~/.ssh/id_rsa`
   - Public key: `~/.ssh/id_rsa.pub`



### Step 3: Copy the Public Key to the Server
1. Use the `ssh-copy-id` command to copy the public key to Machine 2 (Server):
   ```bash
   ssh-copy-id user@<server-ip>
   ```
   - Replace `<server-ip>` with the IP address of Machine 2.
   - Enter the password for the user on Machine 2 when prompted.

2. Alternatively, copy the key manually:
   - Display the public key:
     ```bash
     cat ~/.ssh/id_rsa.pub
     ```
   - Log in to Machine 2 and append the public key to `~/.ssh/authorized_keys`:
     ```bash
     echo "paste-public-key-here" >> ~/.ssh/authorized_keys
     ```
   - Set correct permissions:
     ```bash
     chmod 600 ~/.ssh/authorized_keys
     ```



### Step 4: Test the SSH Connection
1. From Machine 1, SSH into Machine 2 using the configured key:
   ```bash
   ssh user@<server-ip>
   ```
   - Replace `<server-ip>` with the IP address of Machine 2.

2. If the setup is correct, you should connect to Machine 2 without being prompted for a password (unless a passphrase was set for the key).



### Step 5: Optional Security Enhancements
1. Disable Password Authentication on the Server:
   - Edit the SSH configuration file on Machine 2:
     ```bash
     sudo nano /etc/ssh/sshd_config
     ```
   - Set the following parameters:
     ```bash
     PasswordAuthentication no
     ```
   - Restart the SSH service:
     ```bash
     sudo systemctl restart sshd
     ```

2. Restrict Access by IP Address:
   - Use the `/etc/hosts.allow` and `/etc/hosts.deny` files to restrict SSH access.
