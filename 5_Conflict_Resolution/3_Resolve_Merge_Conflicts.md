# How to Resolve Merge Conflicts (Manually and with Tools)

When a merge conflict occurs, Git stops the process so you can decide which changes to keep.  
Conflicts can be resolved **manually** (by editing files) or **with tools** (via editors or Git utilities).

---

## 1. Understanding Conflict Markers

When Git detects a conflict, it marks the conflicting section in your files like this:

```text
<<<<<<< HEAD
const greeting = "Hello, world!";
=======
const greeting = "Hi there!";
>>>>>>> feature/login
````

* `<<<<<<< HEAD` → Your current branch’s version (the branch you’re merging into).
* `=======` → Divider between conflicting changes.
* `>>>>>>> feature/login` → Incoming branch’s version.

You must decide how to combine or choose between them.

---

## 2. Resolving Conflicts **Manually**

### Step 1 — Identify Conflicted Files

```bash
git status
```

Output:

```
both modified:   app.js
```

### Step 2 — Open Each Conflicted File

Look for lines containing:

```
<<<<<<<
=======
>>>>>>>
```

### Step 3 — Edit the File

Manually remove the conflict markers and keep the desired version.

Example (resolved):

```js
const greeting = "Hello there!";
```

### Step 4 — Mark as Resolved

Once fixed, stage the file:

```bash
git add app.js
```

### Step 5 — Complete the Merge

```bash
git commit
```

If you were in a rebase:

```bash
git rebase --continue
```

---

## 3. Resolving Conflicts **Using VS Code**

VS Code automatically detects Git conflicts and provides easy options.

### Steps:

1. Open the conflicted file.
2. You’ll see inline buttons:

   * **Accept Current Change**
   * **Accept Incoming Change**
   * **Accept Both Changes**
   * **Compare Changes**
3. Choose or edit as needed.
4. Save the file → Git automatically marks it as resolved after you `git add`.

---

## 4. Resolving Conflicts with **Git Mergetool**

Git includes a built-in command to launch external merge tools (like `vimdiff`, `meld`, or `kdiff3`).

### Step 1 — Configure a Merge Tool

Example (set Meld as default):

```bash
git config --global merge.tool meld
```

### Step 2 — Launch the Merge Tool

```bash
git mergetool
```

* Opens all conflicted files in your chosen merge tool.
* Let you visually compare and merge differences.

### Step 3 — Finish and Commit

After saving changes:

```bash
git add <file>
git commit
```

---

## 5. Resolving Conflicts on GitHub (Pull Requests)

When merging pull requests, GitHub automatically flags conflicts.
You can fix them directly in the browser:

1. Click **Resolve conflicts**.
2. Edit the file (remove markers, choose correct content).
3. Click **Mark as resolved** → **Commit merge**.

This is ideal for small, simple conflicts.

---

## 6. Aborting a Merge or Rebase

If the merge/rebase is too messy or incorrect, you can cancel it.

### Abort a merge:

```bash
git merge --abort
```

### Abort a rebase:

```bash
git rebase --abort
```

This reverts your working directory to the state before the operation.

---

## 7. Best Practices for Conflict Resolution

✅ **Before merging:**

* Pull latest changes with `git pull --rebase` to reduce conflicts.
* Communicate with teammates working on similar files.

✅ **During merge:**

* Resolve one file at a time.
* Test your code after resolving.

✅ **After merge:**

* Commit clearly (e.g., `"Resolve merge conflict in app.js"`).
* Push resolved branch to remote.

---

## 8. Example Conflict Resolution Workflow

```bash
# 1. Try merging
git merge feature/login

# 2. See conflicts
git status

# 3. Edit files manually or use VS Code
code .

# 4. Mark as resolved
git add app.js

# 5. Complete the merge
git commit

# 6. Push the updated branch
git push origin main
```