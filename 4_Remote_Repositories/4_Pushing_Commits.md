# Pushing Commits

After making commits locally, you need to **push** them to a **remote repository** so others can access your changes.  
`git push` is the command that uploads your local commits, branches, and tags to a remote server such as GitHub, GitLab, or Bitbucket.

---

## 1. What Does `git push` Do?

- Sends local commits to a remote repository.  
- Updates the remote branch to match your local branch.  
- Establishes tracking between local and remote branches (on first push).

---

## 2. Basic Syntax

```bash
git push <remote-name> <branch-name>
````

### Example:

```bash
git push origin main
```

* Pushes your local `main` branch to the `origin` remote repository.

---

## 3. First-Time Push

If your branch doesn’t exist on the remote yet, you can create and push it in one command:

```bash
git push -u origin <branch-name>
```

Example:

```bash
git push -u origin feature/login
```

* The `-u` flag (or `--set-upstream`) links your local branch with the remote one, so future pushes can be done simply with:

```bash
git push
```

---

## 4. Pushing After Making Changes

Typical workflow:

```bash
# Make some changes
git add .
git commit -m "Add new login feature"

# Push the commit to remote repository
git push origin feature/login
```

---

## 5. Pushing All Branches

```bash
git push --all origin
```

* Pushes **all local branches** to the specified remote.

---

## 6. Pushing Tags

You can also push tags to share versioned releases.

```bash
git push origin --tags
```

---

## 7. Force Push (Use with Caution ⚠️)

```bash
git push --force
# or
git push -f
```

* Overwrites the remote branch with your local branch.
* **Dangerous:** It rewrites history and may cause others to lose commits.
* Use only when you understand the impact (e.g., after rebasing).

---

## 8. Common Push Errors

* **Rejected Push:**
  Happens when your local branch is behind the remote.
  Fix by pulling and merging first:

  ```bash
  git pull origin main
  git push origin main
  ```

* **Authentication Failed:**
  Check your credentials or remote URL.

---

## 9. Example Workflow

```bash
# Create a new branch and make a change
git checkout -b feature/signup
git add .
git commit -m "Add signup functionality"

# Push branch to remote
git push -u origin feature/signup

# Continue working and pushing new commits
git add .
git commit -m "Update signup validation"
git push
```