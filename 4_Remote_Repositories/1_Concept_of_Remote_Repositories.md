# Concept of Remote Repositories

A **remote repository** is a version of your project that is hosted on a **server** (e.g., GitHub, GitLab, Bitbucket) and can be **shared with others**. Remote repositories enable **collaboration** and **backup** of your code.

---

## 1. Key Concepts

- **Local repository:** The repository on your machine.  
- **Remote repository:** The repository hosted on a server.  
- **Remote URL:** The address of the remote repository.  
- **Origin:** Default name for the main remote repository.

### Typical Workflow:

```

Local Repository <---> Remote Repository (origin)

````

- You **push** changes from your local repository to the remote.  
- You **pull** changes from the remote to update your local repository.

---

## 2. Common Remote Repository Commands

### Add a remote repository

```bash
git remote add origin <remote-url>
````

* Example:

```bash
git remote add origin https://github.com/username/my-project.git
```

* Adds a remote named `origin` pointing to the URL.

---

### View remote repositories

```bash
git remote -v
```

* Displays URLs of all configured remotes for fetching and pushing.

---

### Push changes to remote

```bash
git push origin main
```

* Pushes commits from your local `main` branch to `origin/main`.

---

### Pull changes from remote

```bash
git pull origin main
```

* Fetches and merges changes from the remote branch into your local branch.

---

### Fetch changes without merging

```bash
git fetch origin
```

* Updates your local copy of remote branches without affecting your working directory.

---

## 3. Collaboration Workflow

1. **Clone a remote repository:**

```bash
git clone <remote-url>
```

* Creates a local copy of the remote repository.

2. **Work on a branch locally**:

```bash
git checkout -b feature/login
```

3. **Push branch to remote**:

```bash
git push origin feature/login
```

4. **Collaborators pull and merge changes**:

```bash
git pull origin main
```