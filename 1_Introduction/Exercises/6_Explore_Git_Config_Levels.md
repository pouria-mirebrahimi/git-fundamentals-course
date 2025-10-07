## Exercise 6: Explore Git Config Levels

**Objective:** Understand the different levels of Git configuration: system, global, and local.

**Instructions:**

```bash
git config --system --list
git config --global --list
git config --local --list
```

**Expected Outcome:**

* You see different configurations depending on the scope.

**Hints:**

* Local config only exists inside a repository.
* Global config is for the current user.
* System config applies to all users on the machine.