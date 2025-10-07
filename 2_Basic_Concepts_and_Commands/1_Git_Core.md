# Core Git Concepts

Understanding Git's core concepts is essential for using it effectively. The main concepts are **repository**, **commit**, and **staging area**.

---

## 1. Repository

A **repository** (or *repo*) is a storage space for your project and its version history.

- **Local repository:** Stored on your computer.
- **Remote repository:** Stored on a server (like GitHub, GitLab, or Bitbucket) and can be shared with others.
- Contains all project files, branches, commits, and metadata in a `.git` folder.

```text
project/
├── .git/          # Git metadata (hidden folder)
├── file1.txt
└── file2.txt
````

---

## 2. Commit

A **commit** is a snapshot of your project at a specific point in time.

* Represents a checkpoint in the project history.
* Includes:

  * Changes staged for commit
  * Commit message describing the changes
  * Author and timestamp

```bash
git commit -m "Add feature X"
```

* Think of a commit as "saving" your progress in Git.

---

## 3. Staging Area

The **staging area** (or *index*) is an intermediate area where Git holds changes before committing them.

* Files must be **added to the staging area** before committing.
* Allows you to prepare commits selectively, including only the changes you want.

```bash
git add file1.txt  # Add specific file
git add .          # Add all changes
```

* After staging, the changes are ready to be committed.

---

### Relationship Between Concepts

```text
Working Directory ---> (git add) ---> Staging Area ---> (git commit) ---> Repository
```

* **Working Directory:** Where you make changes.
* **Staging Area:** Prepares changes for commit.
* **Repository:** Stores committed snapshots permanently.

---

**Tip:** Always check your status with:

```bash
git status
```

This shows which files are staged, modified, or untracked.