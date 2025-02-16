# Lab 2: Basic Workflow

## Agenda
1. **Review of Git Basics**
   - Brief recap of Git initialization and configuration.

2. **Understanding Git Workflow**
   - The stages: Working Directory → Staging Area → Repository.

3. **Hands-on Exercise**
   - Create, modify, and track files using Git commands.
   - Push changes to a remote repository on GitHub or GitLab.

## Objective
By the end of this lab, students will:
- Understand how to stage, commit, and push changes in a Git repository.
- Gain hands-on experience with Git commands for file tracking.
- Push their local commits to a remote repository.

## Steps

### Prerequisites
- Ensure Git is installed and configured (refer to Lab 1).
- Have an account on GitHub or GitLab.

### Step 1: Add a New File to the Repository
1. **Navigate to Your Repository:**
   ```bash
   cd my-first-repo
   ```

2. **Create a New File:**
   ```bash
   echo "This is my second file" > file2.txt
   ```

3. **Check the Status:**
   ```bash
   git status
   ```
   The new file `file2.txt` will appear as untracked.

4. **Stage the File:**
   ```bash
   git add file2.txt
   ```

5. **Confirm the Staging Area:**
   ```bash
   git status
   ```
   The file should now appear under "Changes to be committed."

### Step 2: Make Multiple Changes to the File
1. **Edit the File:**
   Open `file2.txt` in your favorite text editor and add a few lines of text. For example:
   ```
   This is a new line.
   Adding another line for practice.
   ```

2. **Stage the Changes:**
   ```bash
   git add file2.txt
   ```

3. **Commit the Changes:**
   ```bash
   git commit -m "Added file2.txt with initial content"
   ```

### Step 3: Push Changes to a Remote Repository
1. **Create a Remote Repository:**
   - On GitHub or GitLab, create a new repository (e.g., `my-first-repo`).
   - Do not initialize it with a README or any files.

2. **Get the Remote Link:**
   - After creating the repository, GitHub or GitLab will display the remote URL. It looks something like:
     ```
     https://github.com/yourusername/my-first-repo.git
     ```
   - Copy this URL for the next step.

3. **Add Remote Origin:**
   ```bash
   git remote add origin https://github.com/yourusername/my-first-repo.git
   ```
   Replace `yourusername` with your GitHub/GitLab username.

4. **Push Changes:**
   ```bash
   git push -u origin main
   ```
   This pushes your local changes to the remote repository. Use `master` if your branch is named that instead of `main`.

5. **Verify the Push:**
   Visit your GitHub/GitLab repository and confirm that `file2.txt` is visible.

### Additional Step: Make Further Edits and Push Again
1. **Edit the File Again:**
   Add more lines to `file2.txt`, save the changes, and stage them:
   ```bash
   git add file2.txt
   ```

2. **Commit and Push:**
   ```bash
   git commit -m "Updated file2.txt with additional lines"
   git push
   ```

## Deliverables
By the end of this lab, students must:
1. Share the URL of their remote repository (GitHub or GitLab).
2. Provide screenshots showing:
   - The `git status` output before and after staging.
   - The `git log` output showing their commits.
3. Confirm that the file `file2.txt` is visible in the remote repository.
4. Explain the difference between `git add`, `git commit`, and `git push` in their own words.
