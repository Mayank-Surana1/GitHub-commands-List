# GitHub Commands Cheat Sheet

A quick reference for the Git and GitHub commands you will use most often.

## 0. First-Time Setup

| Command | What it Does |
|---|---|
| `git --version` | Checks that Git is installed and shows its version. |
| `git config --global user.name "Your Name"` | Sets the name attached to your commits. |
| `git config --global user.email "you@example.com"` | Sets the email attached to your commits. |
| `git config --global init.defaultBranch main` | Makes `main` the default branch name for new repositories. |
| `git config --list` | Shows all your current Git settings. |

## 1. Setting Up a Repository

| Command | What it Does |
|---|---|
| `git init` | Initializes a brand-new, local Git repository in your current folder. |
| `git clone <URL>` | Downloads an existing repository from GitHub onto your computer. |
| `git clone <URL> <folder-name>` | Clones the repository into a folder with a custom name. |

## 2. Saving Changes (Local Workflow)

| Command | What it Does |
|---|---|
| `git status` | Shows which files have been modified, deleted, or staged. |
| `git add <filename>` | Stages a specific file, preparing it to be saved. |
| `git add .` | Stages all modified and new files in the current directory at once. |
| `git commit -m "your message"` | Saves your staged changes locally with a descriptive message. |
| `git commit -am "your message"` | Stages all modified tracked files and commits them in one step (does not include new files). |
| `git commit --amend -m "new message"` | Rewrites your most recent commit message (avoid after pushing). |

## 3. Syncing with GitHub (Remote Repositories)

| Command | What it Does |
|---|---|
| `git remote add origin <URL>` | Links your local repository to a remote repository on GitHub. |
| `git remote -v` | Lists the remote repositories linked to your project. |
| `git remote set-url origin <URL>` | Changes the URL of an existing remote. |
| `git push -u origin <branch-name>` | Uploads your local commits to GitHub (uses `-u` the first time to set the default branch). |
| `git push` | Uploads local commits to GitHub (after the default branch is set). |
| `git pull` | Fetches the latest updates from GitHub and merges them directly into your local files. |
| `git fetch` | Downloads the latest changes from GitHub without merging them into your files yet. |

## 4. Branches & Collaboration

| Command | What it Does |
|---|---|
| `git branch` | Lists all local branches in your repository (the active one has an asterisk `*`). |
| `git branch -a` | Lists local and remote branches. |
| `git branch <branch-name>` | Creates a new branch with the specified name. |
| `git checkout <branch-name>` | Switches your working environment to a different branch. |
| `git checkout -b <branch-name>` | Shortcut that creates a new branch and immediately switches to it. |
| `git switch <branch-name>` | Modern way to switch to another branch. |
| `git switch -c <branch-name>` | Modern way to create and switch to a new branch. |
| `git merge <branch-name>` | Merges the changes from the specified branch into your current active branch. |
| `git branch -d <branch-name>` | Deletes a local branch that has already been merged. |
| `git push origin --delete <branch-name>` | Deletes a branch on GitHub. |

## ⏪ 5. Inspecting History & Undoing

| Command | What it Does |
|---|---|
| `git log` | Shows a chronological list of all saved commits in the repository. |
| `git log --oneline` | Shows a condensed, clean, one-line version of your commit history. |
| `git log --oneline --graph --all` | Shows history as a visual branch graph. |
| `git show <commit-id>` | Shows the details and changes of a specific commit. |
| `git diff` | Shows the exact line-by-line differences in your unstaged files. |
| `git diff --staged` | Shows the differences in files that are staged but not yet committed. |
| `git reset <file>` | Unstages a file while keeping its physical changes intact. |
| `git checkout -- <file>` | Discards all local changes made to a file since your last commit. |
| `git restore <file>` | Modern way to discard local changes in a file. |
| `git restore --staged <file>` | Modern way to unstage a file. |
| `git reset --soft HEAD~1` | Undoes the last commit but keeps your changes staged. |
| `git reset --hard HEAD~1` | Undoes the last commit and **permanently deletes** the changes. |
| `git revert <commit-id>` | Creates a new commit that safely undoes a previous commit (good for pushed commits). |

## 6. Stashing (Save Work Temporarily)

| Command | What it Does |
|---|---|
| `git stash` | Temporarily shelves your uncommitted changes so you get a clean working folder. |
| `git stash list` | Shows all your saved stashes. |
| `git stash pop` | Re-applies the latest stash and removes it from the stash list. |
| `git stash drop` | Deletes the latest stash. |

## 7. Ignoring & Removing Files

| Command | What it Does |
|---|---|
| `.gitignore` (file) | A file listing patterns (e.g. `node_modules/`, `.env`) that Git should not track. |
| `git rm <file>` | Deletes a file and stages the deletion. |
| `git rm --cached <file>` | Stops tracking a file but keeps it on your computer (useful after adding it to `.gitignore`). |
| `git mv <old> <new>` | Renames or moves a file and stages the change. |

## 8. Tags (Marking Releases)

| Command | What it Does |
|---|---|
| `git tag` | Lists all tags. |
| `git tag v1.0.0` | Creates a lightweight tag at the current commit. |
| `git push origin v1.0.0` | Pushes a specific tag to GitHub. |
| `git push origin --tags` | Pushes all local tags to GitHub. |

## Typical First Upload to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

## Everyday Workflow

```bash
git pull
# ...make your changes...
git add .
git commit -m "Describe what you changed"
git push
```

>  **Tip:** Run `git status` often. It tells you exactly what state your repository is in.
