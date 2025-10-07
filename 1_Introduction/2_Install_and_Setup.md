# Installing and Initial Setup of Git

Let’s get started with setting up Git on your system.

---

## 1. Installing Git

### 🪟 On Windows
1. Go to [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. Download the latest version for Windows.
3. Run the installer and accept the default options.
4. Open **Git Bash** from the Start Menu to confirm installation.

```bash
git --version
```

Expected output:

```
git version 2.x.x
```

---

### 🍏 On macOS

You can install Git via **Homebrew** or **Xcode Command Line Tools**.

```bash
brew install git
```

Or, if Homebrew is not available:

```bash
xcode-select --install
```

Verify:

```bash
git --version
```

---

### 🐧 On Linux

Use your distribution’s package manager:

**Debian/Ubuntu**

```bash
sudo apt update
sudo apt install git
```

**Fedora**

```bash
sudo dnf install git
```

**Arch**

```bash
sudo pacman -S git
```

Verify installation:

```bash
git --version
```

---

## 2. Configuring Git for the First Time

After installation, configure your username and email.
These will be attached to your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

To check your configuration:

```bash
git config --list
```

---

## 3. Setting the Default Branch Name

Newer versions of Git default to the branch name `master`.
You can change it globally to `main` (recommended):

```bash
git config --global init.defaultBranch main
```

---

## 4. Checking Your Settings

View all configurations:

```bash
git config --list
```

Or for a specific key:

```bash
git config user.name
git config user.email
```

---

## 5. Your First Repository

Let’s initialize a new Git repository:

```bash
mkdir my-first-git-project
cd my-first-git-project
git init
```

You’ll see:

```
Initialized empty Git repository in ...
```

This creates a hidden folder called `.git` — Git’s local database where all version history is stored.