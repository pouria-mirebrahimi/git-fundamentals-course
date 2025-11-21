# Undoing Changes in Git

Git provides several ways to undo changes depending on what stage your changes are in and whether you want to modify history or just the working directory.

---

## 1. `git restore`

Used to **discard changes in the working directory** or **unstage files**.

### Discard changes in a file (working directory):

```bash
git restore <file>
```

* Reverts the file to the last committed state.
* Changes will be lost permanently.

### Unstage a file (move from staging area back to working directory):

```bash
git restore --staged <file>
```

* Removes a file from the staging area without touching the working directory.

### Unstage everything:

```bash
git restore --staged .
```

---

Here is your **updated Markdown document** with the new commands for handling **newly created (untracked) files** and fully restoring the working directory added in a clean, consistent style.

You can copy-paste this directly over your existing file.

---

````markdown
# Undoing Changes in Git

Git provides several ways to undo changes depending on what stage your changes are in and whether you want to modify history or just the working directory.

---

## 0. Checking Current State

Before undoing anything, always check:

```bash
git status
````

This shows:

* **Untracked files** → new files not yet tracked by Git
* **Changes not staged for commit** → modified files
* **Changes to be committed** → staged files

---

## 1. `git restore`

Used to **discard changes in the working directory** or **unstage files**.

### Discard changes in a file (working directory):

```bash
git restore <file>
```

* Reverts the file to the last committed state.
* Changes will be lost permanently.

Restore all modified files:

```bash
git restore .
```

### Unstage a file (move from staging area back to working directory):

```bash
git restore --staged <file>
```

* Removes a file from the staging area without touching the working directory.

Unstage everything:

```bash
git restore --staged .
```

---

## 2. `git clean` – Remove Newly Created Files

Used to remove **untracked files and directories** (files not yet added with `git add`).

### Preview what will be deleted (safe dry run)

```bash
git clean -n
```

### Remove untracked files

```bash
git clean -f
```

### Remove untracked files and directories

```bash
git clean -fd
```

⚠️ These files are permanently deleted and cannot be recovered.

---

## 3. `git reset`

Used to **undo commits or unstage changes**. Has different modes:

### Unstage changes (soft reset):

```bash
git reset <file>
```

* Moves the file from the staging area back to the working directory.

### Undo the last commit (keep changes in working directory):

```bash
git reset --soft HEAD~1
```

* Moves `HEAD` back to the previous commit.
* Keeps changes staged.

### Undo the last commit (discard changes completely):

```bash
git reset --hard HEAD~1
```

* Moves `HEAD` back and **removes all changes** in staging and working directory.

**⚠️ Warning:** `--hard` deletes changes permanently.

---

## 4. Full Working Directory Reset (Nuclear Option)

Completely resets the repository to the last commit:

```bash
git reset --hard
git clean -fd
```

This will:

* Remove all local modifications
* Remove all staged changes
* Delete all untracked files and folders

Use only when you are sure.

---

## 5. `git revert`

Used to **undo a commit by creating a new commit**.

```bash
git revert <commit-hash>
```

* Does **not change history**.
* Safest way to undo changes in a shared repository.
* Creates a new commit that **reverses** the changes of the specified commit.

---

### Summary Table

| Command                       | Stage Affected       | Effect                                | Safe for Shared Repo? |
| ----------------------------- | -------------------- | ------------------------------------- | --------------------- |
| `git restore <file>`          | Working Directory    | Discards uncommitted changes          | Yes                   |
| `git restore --staged <file>` | Staging Area         | Unstages changes                      | Yes                   |
| `git reset <file>`            | Staging Area         | Unstages changes                      | Yes                   |
| `git clean -fd`               | Untracked Files      | Deletes new (untracked) files & folders | Yes                 |
| `git reset --soft HEAD~1`     | Commit               | Undo last commit, keep changes staged | No                    |
| `git reset --hard HEAD~1`     | Commit + Working Dir | Undo last commit, discard changes     | No                    |
| `git reset --hard && git clean -fd` | All                  | Full repo reset to last commit          | No                    |
| `git revert <commit>`         | Commit               | Undo commit by creating a new commit  | Yes                   |

---

### Example Workflow

```bash
# Discard changes in a file
git restore file1.txt

# Unstage a file
git restore --staged file1.txt

# Remove new untracked files
git clean -fd

# Undo last commit but keep changes
git reset --soft HEAD~1

# Undo last commit and remove changes
git reset --hard HEAD~1

# Safely revert a commit
git revert abc1234
```