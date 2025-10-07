# Git Cheatsheet

A quick reference for the most common Git commands.

---

## Setup & Configuration

| Action | Command |
|--------|----------|
| Check Git version | `git --version` |
| Set username | `git config --global user.name "Your Name"` |
| Set email | `git config --global user.email "your.email@example.com"` |
| List configuration | `git config --list` |
| Change default branch name | `git config --global init.defaultBranch main` |

---

## Repository Basics

| Action | Command |
|--------|----------|
| Initialize a new repository | `git init` |
| Clone an existing repository | `git clone <url>` |
| Check repository status | `git status` |
| View commit history | `git log` |
| View one-line log | `git log --oneline` |
| Show changes | `git diff` |

---

## Staging & Committing

| Action | Command |
|--------|----------|
| Add all files | `git add .` |
| Add specific file | `git add <file>` |
| Commit changes | `git commit -m "message"` |
| Amend last commit | `git commit --amend` |
| Remove file from staging | `git restore --staged <file>` |

---

## Branching & Merging

| Action | Command |
|--------|----------|
| List branches | `git branch` |
| Create new branch | `git branch <branch>` |
| Switch to branch | `git switch <branch>` or `git checkout <branch>` |
| Create & switch | `git switch -c <branch>` |
| Merge branch | `git merge <branch>` |
| Delete branch | `git branch -d <branch>` |

---

## Remote Repositories

| Action | Command |
|--------|----------|
| Add remote repo | `git remote add origin <url>` |
| View remotes | `git remote -v` |
| Push changes | `git push origin <branch>` |
| Pull updates | `git pull origin <branch>` |
| Clone repo | `git clone <url>` |

---

## Conflict Resolution

| Action | Command |
|--------|----------|
| View conflicts | `git status` |
| Abort merge | `git merge --abort` |
| Use merge tool | `git mergetool` |
| Continue rebase | `git rebase --continue` |
| Abort rebase | `git rebase --abort` |

---

## Inspection & Undo

| Action | Command |
|--------|----------|
| View specific commit | `git show <commit>` |
| Revert a commit | `git revert <commit>` |
| Reset to previous commit | `git reset --hard <commit>` |
| Restore deleted file | `git restore <file>` |

---

## Miscellaneous

| Action | Command |
|--------|----------|
| Create alias | `git config --global alias.<alias> '<command>'` |
| View short log graph | `git log --oneline --graph --decorate --all` |
| Clean untracked files | `git clean -fd` |