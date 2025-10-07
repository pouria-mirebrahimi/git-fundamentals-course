## Exercise 3: Make Commits in Multiple Branches

**Instructions:**

1. On `feature1`, create a file:

```bash
echo "Feature1 code" > feature1.txt
git add feature1.txt
git commit -m "Add feature1 file"
```

2. Switch to `feature2` and create another file:

```bash
echo "Feature2 code" > feature2.txt
git add feature2.txt
git commit -m "Add feature2 file"
```

**Expected Outcome:**

* Each branch has its own commit and file