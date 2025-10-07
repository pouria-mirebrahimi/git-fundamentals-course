## Exercise 5: Revert a Commit

**Objective:** Undo a committed change.

**Instructions:**

1. Make a commit:

```bash
echo "Temporary change" >> hello.txt
git add hello.txt
git commit -m "Temporary commit"
```

2. Revert it:

```bash
git log --oneline
git revert <commit-hash>
```

**Expected Outcome:**

* A new commit appears that undoes the previous commit
* Changes are safely reverted