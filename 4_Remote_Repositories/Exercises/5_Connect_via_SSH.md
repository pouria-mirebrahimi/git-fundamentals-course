## Exercise 5: Connect via SSH (Optional Challenge)

**Instructions:**

1. Generate SSH key:

```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```

2. Add public key to GitHub
3. Verify connection:

```bash
ssh -T git@github.com
```

4. Push changes using SSH URL

**Expected Outcome:**

* SSH connection succeeds
* You can push commits without entering password