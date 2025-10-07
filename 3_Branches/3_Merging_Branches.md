# Merging Branches

Merging is the process of combining changes from one branch into another. It is a key step in integrating features, bug fixes, or updates back into the main branch.

---

## 1. Merge a Branch into Current Branch

### Basic Merge:

```bash
git checkout main          # Switch to the branch you want to merge into
git merge <branch-name>    # Merge the other branch into current branch
````

* Example:

```bash
git checkout main
git merge feature/login
```

* Combines changes from `feature/login` into `main`.
* If there are no conflicts, Git automatically merges changes.

---

## 2. Merge Strategies

* **Fast-forward merge:**

  * Happens when the current branch has no new commits since branching.
  * Git moves `HEAD` forward to the latest commit of the feature branch.
* **Three-way merge:**

  * Happens when both branches have new commits.
  * Git creates a new **merge commit** combining changes.

```text
        A---B---C main
       /
  D---E---F feature
```

After merge (three-way):

```text
        A---B---C---G main
       /         /
  D---E---F feature
```

* `G` is the merge commit.

---

## 3. Handling Merge Conflicts

* Occurs when the same part of a file is changed in both branches.
* Git marks conflicts in the file:

```text
<<<<<<< HEAD
Changes on main
=======
Changes on feature/login
>>>>>>> feature/login
```

* Resolve conflicts manually, then stage and commit:

```bash
git add <file-with-conflict>
git commit
```

---

## 4. Merge vs Rebase (Optional)

* **Merge:** Preserves history; creates a merge commit.
* **Rebase:** Moves your branch’s commits on top of another branch; linear history.

---

## 5. Example Workflow

```bash
# Switch to main branch
git checkout main

# Merge feature branch into main
git merge feature/login

# If conflicts occur:
# 1. Edit conflicting files
# 2. Stage resolved files
git add resolved-file.txt
git commit

# Push merged changes to remote
git push origin main
```