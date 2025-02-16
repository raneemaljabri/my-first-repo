# Lab 1: Git Basics and Setup

## Agenda
1. **Introduction to Git**  
   Overview of version control and the importance of Git in DevOps workflows.

2. **Git Installation**  
   Step-by-step guide to installing Git on various operating systems.

3. **Basic Git Configuration**  
   Setting up user details like username and email for commit tracking.

4. **Initializing a Repository**  
   Creating a new Git repository to start version controlling a project.

5. **File Operations with Git**  
   Adding files, checking repository status, and understanding logs.

## Objective
By the end of this lab, students will:
- Understand the purpose and role of Git in version control.
- Successfully install and configure Git on their system.
- Initialize a new Git repository and perform basic file tracking operations.

## Steps

### Step 1: Install Git
1. **Windows:**  
   - Download the Git installer from [git-scm.com](https://git-scm.com/).
   - Run the installer and follow the on-screen instructions. Ensure you enable Git Bash during the setup.

2. **Linux (Ubuntu/Debian):**  
   ```bash
   sudo apt update
   sudo apt install git
   ```

3. **Mac:**  
   - Install Git using Homebrew:
     ```bash
     brew install git
     ```

4. **Verify Installation:**  
   After installation, open a terminal or Git Bash and type:
   ```bash
   git --version
   ```
   This command should display the installed Git version.

### Step 2: Configure Git
1. **Set Username and Email:**
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "youremail@example.com"
   ```

2. **Verify Configuration:**  
   Check the configuration using:
   ```bash
   git config --list
   ```

### Step 3: Initialize a Repository
1. **Create a Project Directory:**  
   ```bash
   mkdir my-first-repo
   cd my-first-repo
   ```

2. **Initialize the Repository:**  
   ```bash
   git init
   ```
   This creates a new Git repository in the current directory.

3. **Verify Initialization:**  
   Look for the `.git` folder in the project directory by running:
   ```bash
   ls -a
   ```

### Step 4: Create and Track a README File
1. **Create a README File:**  
   ```bash
   echo "# My First Repository" > README.md
   ```

2. **Check Repository Status:**  
   ```bash
   git status
   ```
   This shows that `README.md` is an untracked file.

3. **Track the File:**  
   ```bash
   git add README.md
   ```

4. **Commit the File:**  
   ```bash
   git commit -m "Add README file"
   ```

### Step 5: Explore Repository Logs
1. **View Commit Logs:**  
   ```bash
   git log
   ```
   This displays commit history and details of the last commit.

2. **View Repository Status Again:**  
   ```bash
   git status
   ```
   Confirm there are no pending changes.

## Deliverables
By the end of this lab, students must:
1. Show their configured username and email using `git config --list`.
2. Display a screenshot of their terminal showing the initialized repository (`git init`).
3. Provide a copy of their `README.md` file.
4. Share the commit hash of the first commit from `git log` output.
5. Confirm their Git version and installation method.
