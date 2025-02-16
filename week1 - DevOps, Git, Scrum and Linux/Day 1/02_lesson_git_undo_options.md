# Undoing in Git

## Overview
Mistakes happen, and Git provides powerful tools to undo changes and revert to previous states. This lesson covers various ways to undo changes in Git, from simple modifications to more complex scenarios. You'll learn how to use commands like git restore, git reset, git revert, and git checkout to manage and correct your work.

## Lesson Outcomes
By the end of this lesson, you will be able to:

- Understand different scenarios where undoing changes is necessary.
- Use ```git restore``` to discard changes in the working directory.
- Use ```git reset``` to move the HEAD to a previous commit.
- Use ```git revert``` to create a new commit that undoes changes from a previous commit.
- Use ```git checkout``` to switch branches or restore files from a previous commit.

## Undoing Changes in the Working Directory

### Using ```git restore```

The git restore command is used to discard changes in the working directory. It can restore files to their state in the last commit or the staging area.

**Discard Changes in a File**

To discard changes in a specific file:
```
git restore filename
```

**Discard All Changes**
To discard all changes in the working directory:
```
git restore .
```

### Undoing Changes in the Staging Area

Using ```git restore --staged```

To unstage a file (remove it from the staging area) but keep the changes in the working directory:
```
git restore --staged filename
```

To unstage all files:
```
git restore --staged .
```

Undoing Committed Changes
Using ```git reset```
The git reset command moves the HEAD to a previous commit, effectively undoing commits. It can operate in three modes: --soft, --mixed, and --hard.

### Undoing the Last Commit

**Soft Reset**

A soft reset moves the HEAD to a previous commit but keeps the changes in the staging area:
```
git reset --soft HEAD~1
```

This command undoes the last commit but keeps the changes staged.

### Resetting Commits

**Mixed Reset**

A mixed reset moves the HEAD to a previous commit and keeps the changes in the working directory but unstages them:
```
git reset --mixed HEAD~1
```

This command undoes the last commit and unstages the changes.

## Performing a Hard Reset

**Hard Reset**

A hard reset moves the HEAD to a previous commit and discards all changes in the working directory and staging area:
```
git reset --hard HEAD~1
```

This command undoes the last commit and discards all changes.

## Removing Changes in the Working Directory
Using ```git checkout```
The git checkout command is used to switch branches or restore files from a previous commit.

**Restoring a File from a Previous Commit**
To restore a file to its state in a previous commit:
```
git checkout commit_hash -- filename
```

## Summary
Undoing changes in Git is a common task, and Git provides several commands to handle different scenarios. Use git restore to discard changes in the working directory, git reset to move the HEAD to a previous commit, git revert to create a new commit that undoes changes, and git checkout to switch branches or restore files. These commands help you manage and correct your work efficiently.

## Suggested Reading
- [Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)