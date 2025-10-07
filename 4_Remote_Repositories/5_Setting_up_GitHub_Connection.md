# Setting Up GitHub Connection (HTTPS & SSH)

To collaborate and push code to GitHub, your local Git installation needs to connect securely to your GitHub account.  
There are two main ways to authenticate: **HTTPS** and **SSH**.

---

## 1. HTTPS vs SSH — What’s the Difference?

| Method | Description | Pros | Cons |
|--------|--------------|------|------|
| **HTTPS** | Uses your GitHub username and a **Personal Access Token (PAT)** for authentication. | Simple setup; works on all networks. | You must re-enter credentials unless you use a credential manager. |
| **SSH** | Uses **cryptographic SSH keys** for passwordless authentication. | Secure, no need to re-enter credentials. | Requires one-time setup of SSH keys. |

---

## 2. Connecting via HTTPS

### Step 1 — Clone a Repository Using HTTPS

```bash
git clone https://github.com/<username>/<repository>.git
````

### Step 2 — Set the Remote URL (if you already have a local repo)

```bash
git remote add origin https://github.com/<username>/<repository>.git
```

### Step 3 — Authenticate Using Personal Access Token (PAT)

GitHub no longer supports password-based HTTPS authentication.
You must create a **Personal Access Token**.

#### Create a Token:

1. Go to **GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)**
2. Click **Generate new token**
3. Select scopes like:

   * `repo` (for full repository access)
   * `workflow` (if you use GitHub Actions)
4. Copy your token — you’ll only see it once!

#### Use the Token:

When Git asks for a password during a push or pull, paste your **token** instead of your GitHub password.

Example:

```bash
git push origin main
Username: your-github-username
Password: <paste your PAT here>
```

#### Optional — Store Credentials Securely

```bash
git config --global credential.helper store
```

This saves credentials locally to avoid re-entering them.

---

## 3. Connecting via SSH

### Step 1 — Check for Existing SSH Keys

```bash
ls -al ~/.ssh
```

If you see files like `id_rsa.pub` or `id_ed25519.pub`, you already have an SSH key.

---

### Step 2 — Generate a New SSH Key (if needed)

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

* Press **Enter** to accept default file location.
* Optionally, set a passphrase for extra security.

---

### Step 3 — Start the SSH Agent

```bash
eval "$(ssh-agent -s)"
```

Add your SSH key:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

### Step 4 — Add Your SSH Key to GitHub

1. Copy your public key:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
2. Go to **GitHub → Settings → SSH and GPG keys → New SSH key**
3. Paste the copied key and click **Add SSH key**

---

### Step 5 — Test the SSH Connection

```bash
ssh -T git@github.com
```

Expected output:

```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

---

### Step 6 — Set the SSH Remote URL

```bash
git remote set-url origin git@github.com:<username>/<repository>.git
```

Now you can push without entering credentials:

```bash
git push origin main
```

---

## 4. Switching Between HTTPS and SSH

To switch an existing remote between HTTPS and SSH:

```bash
# View current remote
git remote -v

# Change to SSH
git remote set-url origin git@github.com:<username>/<repository>.git

# Or switch to HTTPS
git remote set-url origin https://github.com/<username>/<repository>.git
```