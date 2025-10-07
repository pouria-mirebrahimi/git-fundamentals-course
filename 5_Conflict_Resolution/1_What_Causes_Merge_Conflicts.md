# What Causes Merge Conflicts

A **merge conflict** occurs when Git cannot automatically combine changes from two branches because both have modified the same parts of a file in incompatible ways.

Conflicts are a normal part of collaboration — they indicate that multiple people (or branches) edited overlapping sections of code or content.

---

## 1. When Do Merge Conflicts Happen?

Merge conflicts can occur during operations like:

| Command | Situation |
|----------|------------|
| `git merge` | When merging branches that have conflicting changes. |
| `git pull` | When pulling remote changes that conflict with your local commits. |
| `git rebase` | When replaying commits onto a new base branch that already has different changes. |
| `git cherry-pick` | When applying a commit that overlaps with existing modifications. |

---

## 2. Common Causes of Merge Conflicts

### **1. Same Line Modified in Two Branches**

Two developers edit the same line of the same file differently.

Example:

- **main branch:**
  ```js
  const greeting = "Hello, world!";
````

* **feature branch:**

  ```js
  const greeting = "Hi there!";
  ```

When you try to merge `feature` into `main`, Git doesn’t know which version to keep — it flags a conflict.

---

### **2. File Deleted in One Branch, Modified in Another**

* **main branch:** The file `config.json` was deleted.
* **feature branch:** Someone updated `config.json`.

Git cannot decide whether to restore or delete the file, so it triggers a conflict.

---

### **3. Changes to the Same File’s Structure**

Reordering or renaming sections in one branch while editing content in another can cause conflicts even if the lines aren’t identical.

Example:

* One branch moves a function to another file.
* Another branch edits that same function.

---

### **4. Concurrent Renames**

If two branches rename a file to different names, Git can’t decide which rename should win.

Example:

* **Branch A:** Renames `utils.js` → `helpers.js`
* **Branch B:** Renames `utils.js` → `utilities.js`

Result → Conflict during merge.

---

## 3. How Git Marks a Conflict

When a conflict occurs, Git stops the merge and marks the file like this:

```text
<<<<<<< HEAD
const greeting = "Hello, world!";
=======
const greeting = "Hi there!";
>>>>>>> feature
```

* `<<<<<<< HEAD` → Your current branch’s version
* `=======` → Divider
* `>>>>>>> feature` → Incoming branch’s version

You must manually edit the file to choose or combine changes, then stage and commit the resolution.

---

## 4. How to Resolve a Conflict

### Step 1 — Check Conflicted Files

```bash
git status
```

Conflicted files will be listed as:

```
both modified:   app.js
```

### Step 2 — Open and Edit the Files

Manually fix the code by keeping one version, combining both, or writing a new one.

Example:

```js
const greeting = "Hello there!";
```

### Step 3 — Mark as Resolved

```bash
git add app.js
```

### Step 4 — Complete the Merge

```bash
git commit
```

or if you were in the middle of a rebase:

```bash
git rebase --continue
```

---

## 5. Tips to Avoid Merge Conflicts

* Pull (`git pull --rebase`) frequently to stay updated.
* Commit small, focused changes.
* Communicate with your team before large refactors.
* Use feature branches for isolated work.
* Avoid editing the same file across multiple active branches.