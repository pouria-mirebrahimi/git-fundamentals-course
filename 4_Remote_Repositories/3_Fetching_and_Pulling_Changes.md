# Fetching and Pulling Changes

When collaborating with others, your local repository can get out of sync with the remote one. Git provides two key commands to **update your local copy**: `git fetch` and `git pull`.

---

## 1. Understanding the Difference

| Command        | Description |
|----------------|-------------|
| `git fetch`    | Downloads new commits and branches from the remote, but **does not change your working directory**. |
| `git pull`     | Fetches and then **merges** (or rebases) the changes from the remote branch into your current branch. |

---

## 2. `git fetch`

### Basic Syntax:

```bash
git fetch
````

* Downloads all updates (commits, branches, tags) from the remote repository.
* Your local branches are **not changed**.
* Lets you review changes before merging.

### Example:

```bash
git fetch origin
```

* Fetches updates from the remote named `origin`.

After fetching, you can compare your branch with the remote one:

```bash
git log HEAD..origin/main
```

* Shows commits that are in `origin/main` but not yet in your local `main`.

---

## 3. `git pull`

### Basic Syntax:

```bash
git pull
```

* Fetches updates and automatically merges them into your current branch.

### Example:

```bash
git pull origin main
```

* Fetches and merges the latest changes from `origin/main` into your local `main`.

If you prefer a **rebase instead of merge**, use:

```bash
git pull --rebase origin main
```

* Keeps history linear by replaying your commits on top of the fetched commits.

---

## 4. Workflow Example

```bash
# Fetch new changes from remote
git fetch origin

# Review what changed
git log HEAD..origin/main

# Merge or rebase as needed
git merge origin/main
# or
git rebase origin/main

# Alternatively, do it all in one step
git pull origin main
```

---

## 5. Common Use Cases

* **Use `git fetch`** when you want to preview changes without altering your local branch.
* **Use `git pull`** when you’re ready to integrate the remote updates into your local work.

---

## 6. Example Output Visualization

```
Before fetch:
main (local): A---B
origin/main:  A---B---C---D

After fetch:
main (local): A---B
origin/main:  A---B---C---D

After pull:
main (local): A---B---C---D
```