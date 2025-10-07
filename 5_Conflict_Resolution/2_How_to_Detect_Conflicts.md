# How to Detect Conflicts

Detecting merge conflicts early helps prevent lost work and makes collaboration smoother.  
Git provides several ways to identify potential or existing conflicts — before, during, and after merges or pulls.

---

## 1. When Git Automatically Detects Conflicts

Git will **pause an operation** (like `merge`, `rebase`, or `pull`) when it detects conflicting changes.  
You’ll see a message like this:

```

Auto-merging app.js
CONFLICT (content): Merge conflict in app.js
Automatic merge failed; fix conflicts and then commit the result.

````

This means one or more files have changes that Git cannot automatically combine.

---

## 2. Check for Conflicts After a Merge or Pull

Use:

```bash
git status
````

Output example:

```
On branch main
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   app.js
```

Any files listed as **“both modified”** or **“unmerged paths”** have conflicts that need to be resolved.

---

## 3. Detect Conflicts Before Merging (Dry Run)

If you want to check for possible conflicts **before actually merging**, you can run:

```bash
git merge --no-commit --no-ff <branch>
```

* Git attempts to merge but stops before committing.
* If there are conflicts, it will report them.
* You can then abort the test merge:

```bash
git merge --abort
```

---

## 4. Detect Conflicts Before Rebasing

During a rebase, Git applies each commit one by one.
To preview possible conflicts before starting a rebase:

```bash
git fetch origin
git diff --name-only --diff-filter=U
```

This command lists files that would conflict if you tried to rebase or merge now.

---

## 5. Detect Conflicts with `git diff`

You can compare branches directly to see overlapping changes.

Example:

```bash
git diff main feature/login
```

This shows differences between two branches.
If both branches modify the same parts of a file, that’s a potential conflict zone.

---

## 6. Detect Conflicts After Git Operations

To explicitly list unresolved conflicts:

```bash
git diff --name-only --diff-filter=U
```

Output example:

```
app.js
config.json
```

These are files with unresolved merge markers (`<<<<<<<`, `=======`, `>>>>>>>`).

---

## 7. Detect Conflict Markers in Code

You can search your project for unresolved markers:

```bash
grep -r '<<<<<<< HEAD' .
```

This scans all files for Git’s conflict markers — useful after large merges or rebases.

---

## 8. Use GUI Tools or IDEs

Modern editors and Git tools make conflict detection easier:

* **VS Code:** Highlights conflicts visually with options to "Accept Current / Incoming / Both Changes".
* **GitKraken / Sourcetree:** Show conflict status per file before committing.
* **GitHub / GitLab:** Automatically detect and mark conflicts during pull requests.

---

## 9. Summary Table

| Situation             | Command / Method                         | Purpose                               |
| --------------------- | ---------------------------------------- | ------------------------------------- |
| After a merge or pull | `git status`                             | See if there are unmerged files.      |
| Preview before merge  | `git merge --no-commit --no-ff <branch>` | Test merge for conflicts.             |
| After operation       | `git diff --name-only --diff-filter=U`   | List files with unresolved conflicts. |
| Search manually       | `grep -r '<<<<<<< HEAD' .`               | Find conflict markers.                |