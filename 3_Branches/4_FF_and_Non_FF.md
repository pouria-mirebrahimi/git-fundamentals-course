# Fast-Forward vs Non-Fast-Forward Merges

Understanding the difference between fast-forward and non-fast-forward merges helps you **maintain a clean and meaningful commit history**.

---

## 1. Fast-Forward Merge

A **fast-forward (FF) merge** occurs when the branch being merged has all its commits ahead of the current branch, and the current branch has no new commits.

### Example:

```

main:    A---B
feature:       C---D

````

- If `main` has no new commits after branching, merging `feature` into `main` just moves `main`’s pointer forward.

```bash
git checkout main
git merge feature
````

Result:

```
main: A---B---C---D
feature:       C---D
```

* **No merge commit is created.**
* History remains linear.

---

## 2. Non-Fast-Forward Merge

A **non-fast-forward (three-way) merge** occurs when both branches have new commits since the branch split.

### Example:

```
main:    A---B---E
feature:       C---D
```

* Merging `feature` into `main` requires Git to create a **merge commit** to combine changes.

```bash
git checkout main
git merge feature
```

Result:

```
main:    A---B---E---M
               \   /
feature:       C---D
```

* `M` is the merge commit combining both histories.
* Preserves the context of parallel development.

---

## 3. When to Use Each

| Merge Type       | Use Case                                                                     |
| ---------------- | ---------------------------------------------------------------------------- |
| Fast-Forward     | Simple updates, linear history, main branch has no new commits               |
| Non-Fast-Forward | Parallel development, multiple contributors, preserve feature branch history |

---

## 4. Force a Merge Commit

Even if a fast-forward merge is possible, you can **force a merge commit** to preserve branch context:

```bash
git merge --no-ff feature/login
```

* Creates a merge commit even for fast-forward scenarios.
* Useful for keeping track of feature branches in history.

---

## 5. Summary

* **Fast-forward:** No merge commit, linear history, simple updates.
* **Non-fast-forward:** Merge commit created, preserves history of multiple branches.
* **Best practice:** Use `--no-ff` for feature branches in team projects to maintain clear history.

```