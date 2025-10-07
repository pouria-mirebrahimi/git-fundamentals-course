# Undoing Changes in Git

Git provides several ways to undo changes depending on what stage your changes are in and whether you want to modify history or just the working directory.

---

## 1. `git restore`

Used to **discard changes in the working directory** or **unstage files**.

### Discard changes in a file (working directory):

```bash
git restore <file>
````

* Reverts the file to the last committed state.
* Changes will be lost permanently.

### Unstage a file (move from staging area back to working directory):

```bash
git restore --staged <file>
```

* Removes a file from the staging area without touching the working directory.

---

## 2. `git reset`

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

## 3. `git revert`

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
| `git reset --soft HEAD~1`     | Commit               | Undo last commit, keep changes staged | No                    |
| `git reset --hard HEAD~1`     | Commit + Working Dir | Undo last commit, discard changes     | No                    |
| `git revert <commit>`         | Commit               | Undo commit by creating a new commit  | Yes                   |

---

### Example Workflow

```bash
# Discard changes in a file
git restore file1.txt

# Unstage a file
git restore --staged file1.txt

# Undo last commit but keep changes
git reset --soft HEAD~1

# Undo last commit and remove changes
git reset --hard HEAD~1

# Safely revert a commit
git revert abc1234
```