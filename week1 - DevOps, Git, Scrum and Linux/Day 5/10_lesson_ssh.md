## Detailed Guide: SSH and Public-Private Key Pairs



## Lesson Overview

Secure Shell (SSH) is a protocol that provides secure access to remote systems over an unsecured network. It is widely used for remote login, file transfers, and executing commands on remote servers. SSH utilizes encryption for secure communication, often enhanced by public and private key pairs for authentication.

This guide explains SSH, the concept of public and private key pairs, their generation, and secure usage.



## Learning Objectives

By the end of this guide, learners will be able to:

1. Understand the basics of SSH and its significance.
2. Explain the concept of public and private key pairs and how they enhance security.
3. Generate, configure, and use SSH key pairs for secure access.
4. Troubleshoot common SSH issues and secure SSH configurations.



## 1. What is SSH?

SSH (Secure Shell) is a cryptographic network protocol that provides secure communication between a client and a server. It is commonly used for:
- Remote login to servers.
- Secure file transfers using tools like `scp` and `sftp`.
- Tunneling and forwarding ports.

### Key Features of SSH:
- End-to-end encryption for secure communication.
- User authentication using passwords or key pairs.
- Integrity checks to ensure data is not tampered with during transmission.



## 2. How SSH Works

1. Connection Initiation:
   - The client initiates a connection to the SSH server on port `22` (default).

2. Server Authentication:
   - The server presents its public key to the client to establish trust.

3. User Authentication:
   - The user authenticates using either a password or an SSH key pair.

4. Encrypted Communication:
   - Once authenticated, all communication between the client and server is encrypted.



## 3. Concept of Public and Private Key Pairs

### What are Public and Private Keys?
- A public-private key pair is a cryptographic mechanism used for secure communication.
- Private Key: A secret key that remains with the user and must never be shared.
- Public Key: A key that can be shared publicly and is used to encrypt data.

### How They Work Together:
1. The server stores the public key.
2. The client uses the private key to prove its identity.
3. The server verifies the client by checking if the private key matches the stored public key.

This eliminates the need for passwords, enhancing security and enabling automated processes.



## 4. Generating SSH Key Pairs

SSH keys are generated using the `ssh-keygen` command.

### Step-by-Step Key Generation:
1. Open a terminal on the client system.
2. Run the following command:
   ```bash
   ssh-keygen -t rsa -b 4096
   ```
   - `-t rsa`: Specifies the key type (RSA).
   - `-b 4096`: Sets the key length (4096 bits for enhanced security).

3. Save the key pair:
   - You’ll be prompted to specify a location to save the key.
   - By default, keys are stored in `~/.ssh/id_rsa` (private) and `~/.ssh/id_rsa.pub` (public).

4. (Optional) Add a passphrase:
   - Enhances security by requiring the passphrase to use the private key.



## 5. Copying the Public Key to the Server

To enable key-based authentication, the public key must be added to the server.

### Using `ssh-copy-id`:
1. Copy the public key to the server:
   ```bash
   ssh-copy-id user@server_ip
   ```
2. Enter the server password when prompted.

### Manual Method:
1. Open the public key file:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
2. Copy the content and append it to the `authorized_keys` file on the server:
   ```bash
   echo "public_key_content" >> ~/.ssh/authorized_keys
   ```
3. Set correct permissions:
   ```bash
   chmod 600 ~/.ssh/authorized_keys
   ```



## 6. Connecting Using SSH Keys

After setting up the keys, connect to the server using:
```bash
ssh user@server_ip
```

- The private key will automatically authenticate the user without requiring a password.



## 7. Securing SSH

### Disable Password Authentication:
1. Open the SSH configuration file on the server:
   ```bash
   sudo nano /etc/ssh/sshd_config
   ```
2. Disable password authentication by adding or updating:
   ```bash
   PasswordAuthentication no
   ```
3. Restart the SSH service:
   ```bash
   sudo systemctl restart sshd
   ```

### Change the Default SSH Port:
1. Edit the SSH configuration file:
   ```bash
   sudo nano /etc/ssh/sshd_config
   ```
2. Change the default port:
   ```bash
   Port 2222
   ```
3. Restart SSH:
   ```bash
   sudo systemctl restart sshd
   ```

### Restrict Root Login:
1. In the SSH configuration file, set:
   ```bash
   PermitRootLogin no
   ```
2. Restart the SSH service.



## 8. Advanced SSH Features

### SSH Agent:
- Use `ssh-agent` to manage private keys and avoid entering passphrases repeatedly.
- Add a key to the agent:
  ```bash
  ssh-add ~/.ssh/id_rsa
  ```

### Port Forwarding:
1. Local port forwarding:
   ```bash
   ssh -L local_port:destination_ip:remote_port user@server_ip
   ```
2. Remote port forwarding:
   ```bash
   ssh -R remote_port:destination_ip:local_port user@server_ip
   ```

### SSH Tunneling:
- Encrypt traffic through an SSH tunnel for secure communication.



## 9. Troubleshooting SSH Issues

### Common Errors:
1. Permission Denied (Public Key):
   - Ensure `~/.ssh/authorized_keys` exists on the server.
   - Check file permissions:
     ```bash
     chmod 600 ~/.ssh/authorized_keys
     chmod 700 ~/.ssh
     ```

2. Connection Refused:
   - Ensure the SSH service is running:
     ```bash
     sudo systemctl status sshd
     ```

3. Key Mismatch:
   - Verify the public key on the server matches the private key on the client.



## 10. Practical Examples

### 1. Connecting to a Server:
```bash
ssh user@192.168.1.100
```

### 2. Copying Files with SCP:
```bash
scp file.txt user@192.168.1.100:/path/to/destination
```

### 3. Executing a Command Remotely:
```bash
ssh user@192.168.1.100 "ls -l /var/www"
```