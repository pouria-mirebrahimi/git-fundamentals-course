# Creating and Switching Branches

Working with branches is essential for managing multiple lines of development. This section covers **how to create, switch, and manage branches** effectively.

---

## 1. Create a New Branch

### Create a branch without switching:

```bash
git branch <branch-name>
````

* Example:

```bash
git branch feature/login
```

* Creates the branch but keeps you on the current branch.

---

### Create and switch to a branch in one step:

```bash
git switch -c <branch-name>
# or
git checkout -b <branch-name>
```

* Example:

```bash
git switch -c feature/login
```

* Creates the branch and moves `HEAD` to it.

---

## 2. Switch Between Branches

```bash
git switch <branch-name>
# or
git checkout <branch-name>
```

* Moves `HEAD` to the specified branch.
* Your working directory updates to reflect the branch’s latest commit.

---

## 3. View Branches

* List **local branches**:

```bash
git branch
```

* List **remote branches**:

```bash
git branch -r
```

* List **all branches (local + remote)**:

```bash
git branch -a
```

---

## 4. Practical Example

```bash
# Start on main branch
git checkout main

# Create and switch to a new feature branch
git switch -c feature/login

# Make changes, stage, and commit
git add .
git commit -m "Implement login feature"

# Switch back to main branch
git switch main

# Merge changes from feature branch
git merge feature/login

# Delete the feature branch locally and remotely
git branch -d feature/login
git push origin --delete feature/login
```