## Exercise 2: Resolve the Conflict Manually

**Instructions:**

1. Open `notes.txt` and you’ll see conflict markers:

```text
<<<<<<< HEAD
Change from branch A
=======
Change from branch B
>>>>>>> branchB
```

2. Edit the file to combine the changes:

```text
Line 1
Change from branch A and branch B
```

3. Save and stage the file:

```bash
git add notes.txt
git commit
```

**Expected Outcome:**

* Merge completes successfully
* History contains a merge commit