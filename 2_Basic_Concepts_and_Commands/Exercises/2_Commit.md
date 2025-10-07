## Exercise 2: Add and Commit a File

**Objective:** Track and commit a file.

**Instructions:**

1. Create a file:

```bash
echo "Hello Git" > hello.txt
```

2. Stage it:

```bash
git add hello.txt
```

3. Commit:

```bash
git commit -m "Add hello.txt"
```

**Expected Outcome:**

* File is staged and committed
* `git log --oneline` shows your commit