# Git Basics

## Overview
Git is a distributed version control system that enables developers to track changes, collaborate efficiently, and manage codebases. It is a critical tool for modern software development, empowering teams to work together on projects of any size. In this lesson, we will cover the fundamentals of Git, including installation, configuration, and key workflows.

---

## What is Git?
Git is an open-source version control system that tracks changes in files and allows multiple developers to collaborate. Key features include:

- **Distributed Architecture:** Each user has a complete copy of the repository.
- **Version History:** Every change is recorded and retrievable.
- **Branching and Merging:** Facilitates parallel development.
- **Collaboration:** Enables seamless teamwork.

---

## Installing Git

To use Git, you first need to install it on your system.

### Windows:
1. Download the Git installer from [Git for Windows](https://git-scm.com/download/win).
2. Run the installer and follow the setup wizard.
3. Select options for the default editor, environment, and other preferences.

### macOS:
1. Install Git via Homebrew:
   ```bash
   brew install git
   ```
2. Verify the installation:
   ```bash
   git --version
   ```

### Linux:
1. Use your distribution’s package manager:
   - Debian/Ubuntu:
     ```bash
     sudo apt update
     sudo apt install git
     ```
   - Fedora:
     ```bash
     sudo dnf install git
     ```
2. Verify the installation:
   ```bash
   git --version
   ```

---

## Setting Up Git

Before using Git, you need to configure your user information, which will be associated with your commits.

### Configure User Name and Email:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Verify Configuration:
```bash
git config --list
```

This command will display all your Git configuration settings.

---

## Git Workflow
The basic Git workflow consists of three main areas:

1. **Working Directory:** Your local files and changes.
2. **Staging Area:** Files that are marked for inclusion in the next commit.
3. **Repository:** The committed changes stored in Git.

### Typical Workflow Steps:
1. Modify files in the working directory.
2. Stage changes with `git add`.
3. Commit changes to the repository with `git commit`.

---

## Key Git Commands

### Adding Files to the Staging Area
```bash
git add filename
```
To add all modified files:
```bash
git add .
```

### Committing Changes
```bash
git commit -m "Your commit message"
```
- The commit message should describe the changes made.

### Checking the Status
```bash
git status
```
This command shows the current state of your working directory and staging area.

### Viewing Commit History
```bash
git log
```
To view a summary of commits:
```bash
git log --oneline
```

---

## Branching in Git
Branches allow you to work on different features or fixes independently.

### Creating a New Branch
```bash
git branch branch_name
```

### Switching to a Branch
```bash
git checkout branch_name
```

### Creating and Switching to a New Branch
```bash
git checkout -b new_branch
```

### Viewing Branches
```bash
git branch
```

---

## Merging Branches
To merge changes from one branch into another:

1. Switch to the branch you want to merge into:
   ```bash
   git checkout main
   ```
2. Merge the target branch:
   ```bash
   git merge branch_name
   ```

### Resolving Merge Conflicts
If there are conflicting changes, Git will notify you. Resolve the conflicts manually, then stage the changes and commit:
```bash
git add .
git commit -m "Resolved merge conflicts"
```

---

## Pull and Fetch

### Git Pull
`git pull` updates your local branch with changes from the remote repository. It performs a `fetch` followed by a `merge`.

```bash
git pull origin branch_name
```

### Git Fetch
`git fetch` retrieves changes from the remote repository but does not merge them.
```bash
git fetch origin
```
To merge the fetched changes manually:
```bash
git merge origin/branch_name
```


## Slides
Review the slides for a visual explanation of these topics: [Git Basics Presentation](https://docs.google.com/presentation/d/1mM2adSoB8pyvrlvg983JaVt7VJfIs93fFsybaxodewU/edit?usp=sharing)

---

This guide provides a comprehensive understanding of Git basics, enabling you to manage and collaborate on projects effectively. Use the slides and additional practice to solidify your skills.
