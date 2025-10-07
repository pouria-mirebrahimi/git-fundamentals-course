## Exercise 4: Unstage a File

**Objective:** Practice `git reset`.

**Instructions:**

1. Modify and stage the file:

```bash
echo "Another line" >> hello.txt
git add hello.txt
```

2. Unstage:

```bash
git reset hello.txt
```

**Expected Outcome:**

* File changes remain, but staging area is empty