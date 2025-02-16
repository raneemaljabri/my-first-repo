# Setting Up Git and GitHub Account

## Overview
This lesson will guide you through setting up Git on your local machine and creating a GitHub account. You will also learn how to authenticate your GitHub account using three different methods: Personal Access Token, SSH Authentication, and HTTPS.

## Lesson Outcomes
By the end of this lesson, you will be able to:

- Install Git on your local machine.
- Create and configure a GitHub account.
- Authenticate your GitHub account using a Personal Access Token, SSH, or HTTPS.

## Setting Up Git

### Installing Git

**Windows**

1. Download the Git installer from Git for Windows.
2. Run the installer and follow the setup instructions.
3. Choose the default options for the editor, environment, and other preferences.

**macOS**

1. Install Git using Homebrew:
    ```
    brew install git
    ```
2. Verify the installation:
    ```
    git --version
    ```

**Linux**

1. Use your distribution’s package manager:
    - Debian/Ubuntu:
        ```
        sudo apt update
        sudo apt install git
        ```
    - Fedora:
        ```
        sudo dnf install git
        ```
2. Verify the installation:
    ```
    git --version
    ```

### Configuring Git
Set your user name and email, which will be associated with your commits.

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Verify the configuration:

```
git config --list
```

### Creating a GitHub Account

**GitHub**

GitHub is a web-based platform that allows developers to store, share, and collaborate on code, web pages, and other content. It uses Git, an open source version control system, to track changes to code over time. 

1. Go to GitHub.
2. Click on "Sign up" and follow the instructions to create an account.
3. Verify your email address to complete the setup.

### Authenticating Your GitHub Account

**Option 1: Use a Personal Access Token**

1. **Generate a Personal Access Token:**

    - Go to GitHub and log in.
    - Click on your profile picture in the top-right corner and select "Settings."
    - In the left sidebar, click on "Developer settings."
    - Click on "Personal access tokens" and then "Generate new token."
    - Give your token a name, select the scopes or permissions you need, and click "Generate token."
    - Copy the token and store it securely.
2. Use the Token for Authentication:

    - When prompted for a username and password, use your GitHub username and the personal access token as the password.

**Option 2: Use SSH Authentication**

1. Generate an SSH Key:
    ```
    ssh-keygen -t ed25519 -C "your.email@example.com"
    ```
    - Follow the prompts to save the key (default location is fine) and set a passphrase.

2. Add the SSH Key to the SSH Agent:
    ```
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519
    ```
3. Add the SSH Key to Your GitHub Account:
    - Copy the SSH key to your clipboard:
        ```
        cat ~/.ssh/id_ed25519.pub
        ```
    - Go to GitHub, click on your profile picture, and select "Settings."
    - In the left sidebar, click on "SSH and GPG keys."
    - Click on "New SSH key," give it a title, and paste the key into the "Key" field.
    - Click "Add SSH key."
4. Test the SSH Connection:
    ```
    ssh -T git@github.com
    ```

**Option 3: Use HTTPS (Deprecated by GitHub)**

1. Clone a Repository Using HTTPS:
    ```
    git clone https://github.com/username/repository.git
    ```
2. Push Changes Using HTTPS:
    ```
    git push https://github.com/username/repository.git
    ```
3. Enter Your GitHub Credentials:
    - When prompted, enter your GitHub username and password.

## Summary
You have now set up Git on your local machine, created a GitHub account, and learned how to authenticate using a Personal Access Token, SSH, and HTTPS. These steps will enable you to manage your repositories and collaborate with others effectively.

## Suggested Reading
- [Git Documentation](https://git-scm.com/doc)

- [GitHub Documentation](https://docs.github.com/en)

- [Generating a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

- [Creating a personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)