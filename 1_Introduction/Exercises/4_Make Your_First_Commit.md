## Exercise 4: Make Your First Commit

**Objective:** Add a file and commit it to your repository.

**Instructions:**

1. Create a file:

```bash
echo "My first Git commit" > note.txt
```

2. Add the file to staging:

```bash
git add note.txt
```

3. Commit the file:

```bash
git commit -m "Initial commit"
```

4. View your commit history:

```bash
git log
```

**Expected Outcome:**

* The commit appears in the log with your message and author info.

**Hints:**

* Use `q` to exit the log view.
