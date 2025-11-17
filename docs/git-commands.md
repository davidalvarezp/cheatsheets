<link rel="stylesheet" href="style.css">

# Git Cheat Sheet

## Stage & Snapshot

Working with snapshots and the Git staging area.

| Command | Description |
|---------|-------------|
| `git status` | Show modified files in the working directory, staged for your next commit. |
| `git add [file]` | Stage a file as it looks now for the next commit. |
| `git reset [file]` | Unstage a file while keeping changes in working directory. |
| `git diff` | Show changes not staged yet. |
| `git diff --staged` | Show changes staged but not committed. |
| `git commit -m "[descriptive message]"` | Commit staged content as a new snapshot. |

---

## Setup

Configuring user information used across all local repositories.

| Command | Description |
|---------|-------------|
| `git config --global user.name "[firstname lastname]"` | Set name for commit history. |
| `git config --global user.email "[valid-email]"` | Set email for commits. |
| `git config --global color.ui auto` | Enable automatic coloring in Git output. |

---

## Setup & Init

Initializing and cloning repositories.

| Command | Description |
|---------|-------------|
| `git init` | Initialize an existing directory as a Git repository. |
| `git clone [url]` | Retrieve an entire repository from a hosted location via URL. |

---

## Branch & Merge

Isolating work in branches, switching context, and integrating changes.

| Command | Description |
|---------|-------------|
| `git branch` | List all branches; `*` indicates current branch. |
| `git branch [branch-name]` | Create a new branch at the current commit. |
| `git checkout [branch]` | Switch to another branch. |
| `git merge [branch]` | Merge specified branch into current branch. |
| `git log` | Show commit history of current branch. |

---

## Installation & GUIs

GitHub provides platform-specific installers and GUIs.

- **GitHub for Windows:** [https://windows.github.com](https://windows.github.com)  
- **GitHub for Mac:** [https://mac.github.com](https://mac.github.com)  
- **Git for all platforms:** [http://git-scm.com](http://git-scm.com)  

Education resources: [education.github.com](https://education.github.com)

---

## Share & Update

Retrieving updates from remote repositories and updating local repos.

| Command | Description |
|---------|-------------|
| `git remote add [alias] [url]` | Add a remote URL as an alias. |
| `git fetch [alias]` | Fetch all branches from remote. |
| `git merge [alias]/[branch]` | Merge a remote branch into current branch. |
| `git push [alias] [branch]` | Push local branch commits to remote branch. |
| `git pull` | Fetch and merge commits from tracking remote branch. |

---

## Tracking Path Changes

Versioning file removals and path changes.

| Command | Description |
|---------|-------------|
| `git rm [file]` | Delete file from project and stage removal. |
| `git mv [old-path] [new-path]` | Move or rename a file and stage the change. |
| `git log --stat -M` | Show commits with path changes. |

---

## Temporary Commits

Temporarily store modified files to switch branches.

| Command | Description |
|---------|-------------|
| `git stash` | Save modified/staged changes. |
| `git stash list` | List stashed changes. |
| `git stash pop` | Apply top stash and remove from stack. |
| `git stash drop` | Remove top stash without applying. |

---

## Rewrite History

Rewriting branches, updating commits, and clearing history.

| Command | Description |
|---------|-------------|
| `git rebase [branch]` | Apply commits of current branch on top of specified branch. |
| `git reset --hard [commit]` | Reset staging area and working tree to specified commit. |

---

## Inspect & Compare

Examining logs, diffs, and Git objects.

| Command | Description |
|---------|-------------|
| `git log` | Show commit history of current branch. |
| `git log branchB..branchA` | Show commits in branchA not in branchB. |
| `git log --follow [file]` | Show commits that changed file, even across renames. |
| `git diff branchB...branchA` | Show differences in branchA not in branchB. |
| `git show [SHA]` | Show any Git object in human-readable format. |

---

## Ignoring Patterns

Prevent staging or committing unwanted files.

| Command | Description |
|---------|-------------|
| `git config --global core.excludesfile [file]` | Use system-wide ignore patterns. |
| `.gitignore` `logs/` `.notes` `pattern/` | Example `.gitignore` patterns. |
