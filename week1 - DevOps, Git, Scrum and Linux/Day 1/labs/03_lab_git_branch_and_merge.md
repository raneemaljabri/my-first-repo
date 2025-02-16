# Lab 3: Branching and Merging

## Agenda
1. **Introduction to Branching**
   - Understand the purpose of branches in version control.
   - Benefits of using branches for feature development.

2. **Hands-on Exercise**
   - Create a new repository locally and set it up on GitHub.
   - Create, switch, and work with branches.
   - Merge changes into the main branch.
   - Resolve merge conflicts.

## Objective
By the end of this lab, students will:
- Understand how to use branches to manage feature development.
- Learn how to merge branches into the main branch.
- Gain hands-on experience in resolving merge conflicts.

## Steps

### Prerequisites
- Ensure Git is installed and configured (refer to Lab 1).
- Have an account on GitHub.

### Step 1: Create a New Repository Locally
1. **Create a New Directory:**
   ```bash
   mkdir branching-lab
   cd branching-lab
   ```

2. **Initialize a Git Repository:**
   ```bash
   git init
   ```

3. **Create a New File:**
   ```bash
   echo "# Branching Lab" > README.md
   ```

4. **Stage and Commit the File:**
   ```bash
   git add README.md
   git commit -m "Initial commit with README"
   ```

### Step 2: Set Up the Repository on GitHub
1. **Create a Repository on GitHub:**
   - Go to GitHub and create a new repository named `branching-lab`.
   - Do not initialize it with any files.

2. **Add the Remote Repository:**
   ```bash
   git remote add origin https://github.com/yourusername/branching-lab.git
   ```
   Replace `yourusername` with your GitHub username.

3. **Push the Local Repository to GitHub:**
   ```bash
   git branch -M main
   git push -u origin main
   ```

### Step 3: Create a New Branch
1. **Create a New Branch:**
   ```bash
   git branch feature-branch
   ```

2. **Switch to the New Branch:**
   ```bash
   git checkout feature-branch
   ```
   OR (if using newer Git versions):
   ```bash
   git switch feature-branch
   ```

3. **Verify the Current Branch:**
   ```bash
   git branch
   ```
   The active branch will be highlighted with an asterisk (*).

### Step 4: Make Changes in the New Branch
1. **Create or Edit a File:**
   ```bash
   echo "This is a new feature." > feature.txt
   ```

2. **Stage and Commit the Changes:**
   ```bash
   git add feature.txt
   git commit -m "Added feature.txt in feature-branch"
   ```

3. **Check the Commit History:**
   ```bash
   git log --oneline
   ```

### Step 5: Switch Back to the Main Branch and Merge
1. **Switch to the Main Branch:**
   ```bash
   git checkout main
   ```
   OR:
   ```bash
   git switch main
   ```

2. **Merge the Feature Branch:**
   ```bash
   git merge feature-branch
   ```

3. **Verify the Merge:**
   - Check that `feature.txt` is now part of the main branch:
     ```bash
     ls
     ```

4. **View the Commit History:**
   ```bash
   git log --oneline
   ```

### Step 6: Resolve Merge Conflicts
1. **Create a Conflict:**
   - Switch back to `feature-branch` and edit `feature.txt`:
     ```bash
     echo "This is a conflicting line." >> feature.txt
     git commit -am "Added conflicting line in feature-branch"
     ```
   - Switch to the `main` branch and edit `feature.txt` differently:
     ```bash
     echo "This is another conflicting line." >> feature.txt
     git commit -am "Added conflicting line in main"
     ```

2. **Attempt to Merge:**
   ```bash
   git merge feature-branch
   ```
   Git will report a conflict in `feature.txt`.

3. **Resolve the Conflict:**
   - Open `feature.txt` and manually resolve the conflict by editing the file.
   - Stage the resolved file:
     ```bash
     git add feature.txt
     ```
   - Complete the merge:
     ```bash
     git commit -m "Resolved merge conflict in feature.txt"
     ```

4. **Verify the Conflict Resolution:**
   ```bash
   git log --oneline
   ```

## Deliverables
By the end of this lab, students must:
1. Share the URL of their remote repository (GitHub).
2. Provide screenshots of:
   - The `git branch` output showing the feature branch.
   - The commit history (`git log --oneline`) after the merge.
3. Demonstrate the resolved conflict in `feature.txt`.
4. Explain the steps they took to resolve the merge conflict in their own words.
5. Confirm the final state of `feature.txt` in the main branch.
