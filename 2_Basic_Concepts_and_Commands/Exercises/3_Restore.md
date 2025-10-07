## Exercise 3: Modify and Restore

**Objective:** Undo unstaged changes.

**Instructions:**

1. Modify the file:

```bash
echo "New line" >> hello.txt
```

2. Undo changes:

```bash
git restore hello.txt
```

**Expected Outcome:**

* File returns to the previous state