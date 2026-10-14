# Lab 2 Git Workflow Notes

This repository contains notes and examples for common Git operations used during the lab, including branch creation, merging, tagging, and clean-up tasks.

## 1) Initialize and connect the repository

```bash
git init
git add .
git commit -m "lab2"
git remote add origin git@github.com:mazenzakarya/lab2.git
git push origin main
```

- `git init` creates a local Git repository.
- `git add .` stages all changes.
- `git commit -m "lab2"` saves the staged changes.
- `git remote add origin ...` connects the local repo to the remote GitHub repository.
- `git push origin main` uploads the local branch to the remote repository.

## 2) Working with branches

```bash
git branch dev
git branch test
git switch main
git merge dev
git merge test
```

When working on multiple branches:

```bash
git add .
git commit -m "feat: add files on test"
git push origin test
```

This creates and pushes a feature branch named `test`.

## 3) Undo a mistake

```bash
git reset --hard HEAD^
```

This resets the current branch to the previous commit. Use it carefully because it discards recent changes.

## 4) Tag a release version

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin --tags
```

This creates a lightweight annotated tag and pushes all tags to the remote repository.

## 5) Delete local and remote branches

```bash
git branch -d test
git push origin --delete test
```

- `git branch -d test` deletes the local branch.
- `git push origin --delete test` removes the branch from GitHub.

## 6) Save work before switching branches

First check which branch you are on and whether you have changes to save:

```bash
git status
git branch --show-current
```

Save the current changes, including untracked files, then switch branches:

```bash
git stash push -u -m "work before switching branches"
git switch dev
```

When you are ready to return, switch back to the branch you noted earlier. Then check the stash and restore the saved changes:

```bash
git switch main
git stash list
git stash pop
```

`git stash pop` applies the most recent stash to the branch you are currently on and removes it from the stash list if it applies successfully. Make sure you switch back to `<original-branch>` before running it, so the changes are restored to the branch where you started. If you want to apply the changes but keep the stash entry, use `git stash apply` instead. If Git reports conflicts, resolve them and check the result with `git status`.

## 7) Delete a tag locally and remotely

```bash
git tag -d v1.0.0
git push origin --delete v1.0.0
```

Example output:

```bash
Deleted tag 'v1.0.0' (was 6d830d7)
```

## 8) Example final push

```bash
git add .
git commit -m "add img to readme"
git push origin main
```

## 9) Project image

```html
<img src="src/x4-3.jpeg" alt="Project image">
```

<img src="src/x4-3.jpeg" alt="Project image" width="400">

## Quick reference

```bash
# initialize repo
git init

# stage and commit
git add .
git commit -m "message"

# connect remote
git remote add origin <repository-url>

# push branch
git push origin main

# create branch
git branch dev

# switch branch
git switch main

# merge branch
git merge dev

# delete local branch
git branch -d <branch-name>

# delete remote branch
git push origin --delete <branch-name>

# create tag
git tag -a v1.0.0 -m "Release version 1.0.0"

# delete local tag
git tag -d v1.0.0

# delete remote tag
git push origin --delete v1.0.0
```
