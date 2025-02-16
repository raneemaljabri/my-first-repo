# Merging in Git

## Overview
Merging in Git is the process of integrating changes from one branch into another. It's a crucial part of collaborative development, allowing multiple people to work on different features or fixes simultaneously. This lesson covers the basics of merging, strategies to follow, and how to resolve conflicts.

## Lesson Outcomes
By the end of this lesson, you will be able to:

- Understand what merging is and why it's important.
- Perform basic merge operations.
- Use different merging strategies effectively.
- Resolve merge conflicts.
- Handle common merging scenarios.


## What is Merging?
Merging combines changes from different branches. It's essential for integrating new features, bug fixes, or updates from one branch into another, typically the main branch.

## Why Merge?
- **Integrate Features:** Combine work from feature branches into the main codebase.
- **Collaborate:** Allow multiple developers to work on different parts of the project simultaneously.
- **Maintain Stability:** Keep the main branch stable while developing new features in separate branches.

## Basic Merge Operation

### Steps to Merge
1. Switch to the Target Branch:
    ```
    git checkout main
    ```
2. Merge the Source Branch:
    ```
    git merge feature-branch
    ```

*Example*

1. Create and switch to a new branch:
    ```
    git checkout -b new-feature
    ```
2. Make changes and commit them:
    ```
    echo "New feature content" > feature.txt
    git add feature.txt
    git commit -m "Add new feature"
    ```
3. Switch back to the main branch:
    ```
    git checkout main
    ```
4. Merge the new feature branch into main:
    ```
    git merge new-feature
    ```

## Merging Strategies
### Fast-Forward Merge
A fast-forward merge occurs when the main branch has not moved forward since the feature branch was created. Git simply moves the main branch pointer forward to the latest commit of the feature branch.

**Example:**

```
# Assume main branch is at commit A and new-feature branch is at commit B
git checkout main
git merge new-feature  # Main branch moves to commit B
```

### Three-Way Merge
A three-way merge happens when the main branch has moved forward since the feature branch was created. Git creates a new commit that combines the changes from both branches.

Example:
```
# Assume main branch is at commit C and new-feature branch is at commit B
git checkout main
git merge new-feature  # Creates a new commit D that combines changes from C and B
```

### Resolving Merge Conflicts
Conflicts occur when changes in different branches affect the same lines of a file. Git will mark the conflicting areas, and you need to resolve them manually.

### **Steps to Resolve Conflicts**

1. Identify Conflicts:

    Git will mark conflicts in the files with conflict markers (<<<<<<<, =======, >>>>>>>).

2. Edit the Files:

    Manually edit the files to resolve the conflicts.

3. Stage the Resolved Files:
    ```
    git add resolved-file.txt
    ```
4. Commit the Merge:
    ```
    git commit -m "Resolved merge conflicts"
    ```

**Example**

1. Create and switch to a new branch:
    ```
    git checkout -b conflict-branch
    ```
2. Make conflicting changes:
    ```
    echo "Conflicting content" > conflict.txt
    git add conflict.txt
    git commit -m "Add conflicting content"
    ```
3. Switch back to the main branch and make different changes:
    ```
    git checkout main
    echo "Different content" > conflict.txt
    git add conflict.txt
    git commit -m "Add different content"
    ```
4. Attempt to merge the conflict branch:
    ```
    git merge conflict-branch
    ```
5. Resolve conflicts in conflict.txt and commit the resolution:
    ```
    # Edit conflict.txt to resolve conflicts
    git add conflict.txt
    git commit -m "Resolved merge conflicts"
    ```

## Common Merging Scenarios

### Merging a Feature Branch
1. Create a Feature Branch:
    ```
    git checkout -b feature-branch
    ```
2. Develop the Feature:

    Make changes and commit them.

3. Merge into Main:
    ```
    git checkout main
    git merge feature-branch
    ```

### Merging a Hotfix Branch
1. Create a Hotfix Branch:
    ```
    git checkout -b hotfix-branch
    ```
2. Fix the Issue:

    Make changes and commit them.

3. Merge into Main and Develop:
    ```
    git checkout main
    git merge hotfix-branch
    git checkout develop
    git merge hotfix-branch
    ```

## Merging a Release Branch

1. Create a Release Branch:
    ```
    git checkout -b release-branch
    ```
2. Prepare the Release:

    Make final adjustments and commit them.

3. Merge into Main and Develop:
    ```
    git checkout main
    git merge release-branch
    git checkout develop
    git merge release-branch
    ```

## Best Practices
1. Commit Often:

    Make small, frequent commits to keep changes manageable.

2. Pull Before Merging:

    Always pull the latest changes from the main branch before merging.

3. Resolve Conflicts Promptly:

    Address conflicts as soon as they arise to avoid larger issues.

4. Use Descriptive Commit Messages:

    Clear commit messages help track changes and understand the history.

5. Test After Merging:

    Run tests to ensure the merged code works as expected.

## Suggested Reading

- [Git Merge Documentation](https://git-scm.com/docs/git-merge)
