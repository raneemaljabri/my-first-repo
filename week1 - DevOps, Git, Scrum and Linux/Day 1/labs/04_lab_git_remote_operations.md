# Lab 4: Advanced Remote Operations and Stashing

## Agenda
1. **Introduction to Advanced Remote Operations**
   - Learn how to work with multiple remotes in a Git repository.
   - Understand the difference between `git pull` and `git fetch`.

2. **Introduction to Stashing**
   - Understand how to save and manage uncommitted changes using `git stash`.

3. **Hands-on Exercises**
   - Add and manage multiple remotes.
   - Practice pulling and fetching changes from remotes.
   - Save, apply, and drop stashes in different scenarios.

## Objective
By the end of this lab, students will:
- Learn to manage multiple remotes in a Git repository.
- Understand the differences between `git pull` and `git fetch`.
- Use `git stash` to save and retrieve uncommitted changes effectively.

## Steps

### Prerequisites
- Use the `branching-lab` repository created earlier.
- Ensure you have access to another Git hosting service (e.g., GitHub and GitLab accounts).

---

### Part 1: Advanced Remote Operations

#### Step 1: Add Multiple Remotes
1. **Add a New Remote:**
   - Add a secondary remote to your repository:
     ```bash
     git remote add secondary https://gitlab.com/yourusername/branching-lab.git
     ```
     Replace `yourusername` with your GitLab username.

2. **Verify the Remotes:**
   ```bash
   git remote -v
   ```
   **What will you see?**
   A list of remotes (`origin` and `secondary`) with their respective URLs.

#### Step 2: Pull and Fetch Changes
1. **Fetch Changes from the Secondary Remote:**
   ```bash
   git fetch secondary
   ```
   **Why are we doing this?**
   To retrieve references and updates from the `secondary` remote without merging them.

   **What will you see?**
   Remote-tracking branches for `secondary` will appear when you run:
   ```bash
   git branch -r
   ```

2. **Pull Changes from the Origin Remote:**
   ```bash
   git pull origin main
   ```
   **Why are we doing this?**
   To fetch and merge changes from the `origin` remote into your local branch.

   **What will you see?**
   Any new changes from the `main` branch of the `origin` remote will be applied locally.

#### Step 3: Understand the Difference Between `git pull` and `git fetch`
- **`git fetch`:** Downloads changes without modifying your working directory.
- **`git pull`:** Combines `git fetch` and `git merge`, integrating remote changes into your local branch.

---

### Part 2: Stashing

#### Step 1: Save Changes with `git stash`
1. **Modify a File:**
   ```bash
   echo "Temporary change" >> feature.txt
   ```

2. **Save the Changes:**
   ```bash
   git stash
   ```
   **Why are we doing this?**
   To temporarily save uncommitted changes and clean the working directory.

   **What will you see?**
   Running `git status` will show a clean working directory, while `git stash list` will display the saved stash.

#### Step 2: Apply Stashes
1. **Apply the Last Stash:**
   ```bash
   git stash apply
   ```
   **Why are we doing this?**
   To restore the saved changes from the stash without removing them from the stash list.

2. **Drop the Stash After Applying:**
   ```bash
   git stash drop
   ```

   **What will you see?**
   The stash is removed from the list. Verify using:
   ```bash
   git stash list
   ```

#### Step 3: Manage Multiple Stashes
1. **Create Another Stash:**
   ```bash
   echo "Another temporary change" >> feature.txt
   git stash
   ```

2. **View and Apply a Specific Stash:**
   - List all stashes:
     ```bash
     git stash list
     ```
   - Apply a specific stash by its identifier:
     ```bash
     git stash apply stash@{0}
     ```

3. **Clear All Stashes:**
   ```bash
   git stash clear
   ```
   **Why are we doing this?**
   To clean up the stash list when it is no longer needed.

---

## Deliverables
- Screenshots of:
  - The `git remote -v` output showing multiple remotes.
  - The `git stash list` output after saving multiple stashes.
  - Terminal output for applying and dropping stashes.
- Explanation of:
  - The difference between `git pull` and `git fetch`.
  - How they used `git stash` to manage temporary changes.
- Final state of the repository after completing all steps.
