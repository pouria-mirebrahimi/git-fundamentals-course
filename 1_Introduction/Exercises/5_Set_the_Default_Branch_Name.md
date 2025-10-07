## Exercise 5: Set the Default Branch Name

**Objective:** Change Git's default branch name to `main`.

**Instructions:**

```bash
git config --global init.defaultBranch main
mkdir test-repo
cd test-repo
git init
git branch
```

**Expected Outcome:**

* The default branch is `main` instead of `master`.