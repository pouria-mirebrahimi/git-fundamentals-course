# Git Glossary

A reference list of important Git terms.

---

### General Terms

- **Repository (Repo):** A storage space where your project and its version history live.
- **Working Directory:** The current state of files you’re editing.
- **Staging Area (Index):** A holding area before committing changes.
- **Commit:** A snapshot of your repository at a specific time.
- **Branch:** A separate line of development in Git.
- **Merge:** Combining changes from different branches.

---

### Remote Terms

- **Remote:** A version of your repository hosted elsewhere (e.g., GitHub).
- **Origin:** The default name of the remote repository.
- **Fetch:** Download new data from the remote (without merging).
- **Pull:** Fetch + merge remote changes into your branch.
- **Push:** Upload local commits to the remote repository.

---

### Conflict Terms

- **Merge Conflict:** Occurs when two branches modify the same line of a file.
- **Conflict Markers:** Lines added by Git (`<<<<<<<`, `=======`, `>>>>>>>`) to show differences.
- **Merge Tool:** A utility to help visualize and resolve conflicts.

---

### History & Versioning

- **HEAD:** The current branch reference.
- **SHA (Commit Hash):** A unique ID for each commit.
- **Rebase:** Moving or combining commits onto a new base branch.
- **Reset:** Move HEAD to another commit (can modify history).
- **Revert:** Undo a commit safely by creating a new commit.

---

### Configuration Terms

- **Global Config:** Settings applied to all repositories for the current user.
- **Local Config:** Settings specific to one repository.
- **System Config:** Settings for all users on the machine.
