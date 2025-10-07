# Git Basics

This document covers the basic Git commands every developer should know: `init`, `status`, `add`, `commit`, and `log`.

---

## 1. `git init`

Initializes a new Git repository in the current directory.

```bash
git init
````

* Creates a `.git` directory to start tracking changes.
* After this, you can start adding files and committing changes.

---

## 2. `git status`

Displays the state of the working directory and staging area.

```bash
git status
```

* Shows which files are staged, unstaged, or untracked.
* Useful to check what will be committed next.

---

## 3. `git add`

Adds changes in the working directory to the staging area.

```bash
git add <file>
git add .       # Adds all changes
```

* Prepares files to be included in the next commit.
* Can add specific files or all changes at once.

---

## 4. `git commit`

Records changes in the repository with a descriptive message.

```bash
git commit -m "Your commit message"
```

* Commits staged changes to the local repository.
* The `-m` flag allows you to write a commit message inline.

---

## 5. `git log`

Shows the commit history for the repository.

```bash
git log
```

* Displays commits with their SHA, author, date, and message.
* Useful to track changes and history of the project.

---

### Example Workflow

```bash
# Initialize a new repository
git init

# Check repository status
git status

# Add files to staging
git add .

# Commit changes
git commit -m "Initial commit"

# View commit history
git log
```