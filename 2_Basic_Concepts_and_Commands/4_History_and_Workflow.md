# Understanding Git Commit History and Workflow

Git's commit history and workflow help you **track changes**, **collaborate**, and **manage your project efficiently**.

---

## 1. Commit History

The commit history is a **chronological record of all changes** in a repository.

### View commit history:

```bash
git log
````

* Shows commit SHA, author, date, and message.
* Useful to track what was changed, by whom, and when.

### Common options:

```bash
git log --oneline       # Short version of commits
git log --graph         # Visualizes branches and merges
git log --stat          # Shows files changed in each commit
```

### Understanding a commit:

```
commit 1a2b3c4d
Author: Jane Doe <jane@example.com>
Date:   Mon Oct 7 12:34:56 2025 +0000

    Add user login feature
```

* **SHA:** Unique identifier of the commit.
* **Author:** Who made the commit.
* **Date:** When it was committed.
* **Message:** Describes the changes.

---

## 2. Git Workflow

A Git workflow is a **structured way to use Git commands** to make changes, track progress, and collaborate.

### Basic Workflow:

```text
Working Directory → (git add) → Staging Area → (git commit) → Local Repository → (git push) → Remote Repository
```

1. **Working Directory:** Where you edit files.
2. **Staging Area:** Prepares changes for commit.
3. **Local Repository:** Stores committed snapshots on your machine.
4. **Remote Repository:** Shared repository for collaboration.

---

### Common Git Workflow Steps

1. **Clone a repository:**

```bash
git clone <repo-url>
```

2. **Make changes in working directory**
   Edit files as needed.

3. **Stage changes:**

```bash
git add <file>
git add .  # Add all changes
```

4. **Commit changes:**

```bash
git commit -m "Describe your changes"
```

5. **View commit history:**

```bash
git log --oneline --graph
```

6. **Push changes to remote repository:**

```bash
git push origin main
```

---

### Branching Workflow (Optional)

* **Branches** allow multiple lines of development.
* Common practice:

```bash
git checkout -b feature/login
git add .
git commit -m "Implement login"
git push origin feature/login
```

* Merge changes back to main branch when ready.