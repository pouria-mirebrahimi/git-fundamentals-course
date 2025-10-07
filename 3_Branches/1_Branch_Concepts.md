# Branch Concept and Workflow

Branches are one of Git’s most powerful features, allowing you to **work on multiple lines of development simultaneously** without affecting the main project.

---

## 1. What is a Branch?

A **branch** is a separate line of development in a Git repository.  

- The **main branch** (often called `main` or `master`) contains stable code.  
- Feature branches allow you to develop new features, fix bugs, or experiment safely.  
- Each branch has its own commit history.  

### Visual Representation

```

main
|
o---o---o

feature
o---o---o

````

- Commits in the `feature` branch are isolated from `main` until merged.

---

## 2. Creating and Switching Branches

### Create a new branch:

```bash
git branch <branch-name>
````

* Creates a branch but **does not switch to it**.

### Switch to a branch:

```bash
git checkout <branch-name>
```

* Moves `HEAD` to the branch you want to work on.

### Create and switch in one step:

```bash
git switch -c <branch-name>
# or
git checkout -b <branch-name>
```

---

## 3. Branch Workflow

A typical Git branch workflow:

1. **Start from main branch:**

```bash
git checkout main
```

2. **Create a feature branch:**

```bash
git switch -c feature/login
```

3. **Make changes and commit:**

```bash
git add .
git commit -m "Implement login feature"
```

4. **Push branch to remote (optional):**

```bash
git push origin feature/login
```

5. **Merge branch back to main when done:**

```bash
git checkout main
git merge feature/login
```

6. **Delete branch after merging (optional):**

```bash
git branch -d feature/login
git push origin --delete feature/login
```

---

## 4. Viewing Branches

* List all local branches:

```bash
git branch
```

* List all remote branches:

```bash
git branch -r
```

* List all branches (local + remote):

```bash
git branch -a
```

---

## 5. Tips for Branch Workflow

* Use **short-lived feature branches** to avoid conflicts.
* Commit **frequently** to capture progress.
* Pull updates from `main` regularly to keep your branch up to date:

```bash
git pull origin main
```

* Use **meaningful branch names** (e.g., `feature/login`, `bugfix/header-style`).