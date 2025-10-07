## Exercise 1: Create a Conflict

**Objective:** Reproduce a merge conflict.

**Instructions:**
1. Create a new repo and make an initial commit:
```bash
mkdir conflict-demo
cd conflict-demo
git init
echo "Line 1" > notes.txt
git add notes.txt
git commit -m "Initial commit"
````

2. Create two branches:

```bash
git branch branchA
git branch branchB
```

3. Edit the same file differently in both branches.

On `branchA`:

```bash
git switch branchA
echo "Change from branch A" >> notes.txt
git commit -am "Edit from branch A"
```

On `branchB`:

```bash
git switch branchB
echo "Change from branch B" >> notes.txt
git commit -am "Edit from branch B"
```

4. Merge `branchB` into `branchA`:

```bash
git switch branchA
git merge branchB
```

**Expected Outcome:**

* A merge conflict occurs.