# Introduction to Rebase

Git **rebase** is an alternative to merging that allows you to **move or combine commits from one branch onto another**, creating a linear history.

---

## 1. What is Rebase?

- Rebase takes commits from one branch and **reapplies them onto another branch**.
- Unlike `merge`, it **does not create a merge commit**.
- Often used to **keep feature branches up to date** with the main branch before merging.

### Example:

```

main:    A---B
feature:       C---D

````

```bash
git checkout feature
git rebase main
````

Result:

```
main:    A---B
feature:       C'---D'
```

* Commits `C` and `D` are replayed on top of `B`.
* History is now linear, as if `feature` was created from the latest `main`.

---

## 2. Rebase vs Merge

| Aspect        | Merge                           | Rebase                            |
| ------------- | ------------------------------- | --------------------------------- |
| History       | Non-linear, merge commits added | Linear, no merge commits          |
| Collaboration | Safe for shared branches        | Should not rebase shared branches |
| Use case      | Preserve parallel development   | Clean, linear history             |

---

## 3. Updating Feature Branch with Main

```bash
# Switch to your feature branch
git checkout feature

# Rebase onto main
git rebase main
```

* If conflicts occur, Git pauses and allows you to resolve them:

```bash
# Resolve conflicts in files
git add <file>
git rebase --continue
```

* To abort the rebase and return to original state:

```bash
git rebase --abort
```

---

## 4. Interactive Rebase

Interactive rebase allows editing, squashing, or reordering commits:

```bash
git rebase -i HEAD~3
```

* Opens a text editor with the last 3 commits.
* You can:

  * `pick` → keep commit as-is
  * `squash` → combine commits
  * `edit` → modify commit
  * `reword` → change commit message

---

## 5. Best Practices

* Only rebase **local branches** or branches not yet pushed/shared.
* Rebase **frequently** to stay updated with `main`.
* Use `git log --oneline --graph` to visualize history before and after rebasing.