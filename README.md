# Git Fundamentals Course

Welcome to the **Git Fundamentals Course** — a structured, hands-on learning path designed to take you from **beginner to confident Git user**.  
This course is ideal for software developers, data scientists, and anyone collaborating on version-controlled projects.

---

## Overview

You’ll learn:
- How to install and configure Git  
- Core Git concepts and commands  
- Branching and merging strategies  
- Working with remote repositories (GitHub, GitLab, etc.)  
- Resolving merge conflicts  
- Structuring and managing real-world projects  

Each lesson includes:
- **Concept explanations** (`.md` files)  
- **Hands-on exercises** (`Exercises/`)  
- **Cheat sheets and references** (`resources/`)  

---

## Repository Structure

```

├── 1_Introduction
│   ├── 1_Prerequisites.md
│   ├── 2_Install_and_Setup.md
│   ├── Exercises
│   │   ├── 1_Setup_Practice.md
│   │   ├── 2_Configure_Your_Identity.md
│   │   ├── 3_Initialize_a_Local_Repository.md
│   │   ├── 4_Make_Your_First_Commit.md
│   │   ├── 5_Set_the_Default_Branch_Name.md
│   │   └── 6_Explore_Git_Config_Levels.md
│   └── README.md
│
├── 2_Basic_Concepts_and_Commands
│   ├── 1_Git_Core.md
│   ├── 2_Git_Basics.md
│   ├── 3_Undoing_Changes.md
│   ├── 4_History_and_Workflow.md
│   ├── Exercises
│   │   ├── 1_Initialize.md
│   │   ├── 2_Commit.md
│   │   ├── 3_Restore.md
│   │   ├── 4_Unstage_File.md
│   │   └── 5_Revert_Commit.md
│   └── README.md
│
├── 3_Branches
│   ├── 1_Branch_Concepts.md
│   ├── 2_Creating_and_Switching.md
│   ├── 3_Merging_Branches.md
│   ├── 4_FF_and_Non_FF.md
│   ├── 5_Rebase.md
│   ├── Exercises
│   │   ├── 1_Create_Branch.md
│   │   ├── 2_Create_and_Switch.md
│   │   ├── 3_Commit_in_Multiple_Branches.md
│   │   ├── 4_Merge_Branch.md
│   │   ├── 5_Resolve_Merge_Conflict.md
│   │   └── 6_Deleting_Branch.md
│   └── README.md
│
├── 4_Remote_Repositories
│   ├── 1_Concept_of_Remote_Repositories.md
│   ├── 2_Cloning_Repository.md
│   ├── 3_Fetching_and_Pulling_Changes.md
│   ├── 4_Pushing_Commits.md
│   ├── 5_Setting_up_GitHub_Connection.md
│   ├── Exercises
│   │   ├── 1_Add_Remote.md
│   │   ├── 2_Clone_Repository.md
│   │   ├── 3_Fetch_and_Pull.md
│   │   ├── 4_Push.md
│   │   └── 5_Connect_via_SSH.md
│   └── README.md
│
├── 5_Conflict_Resolution
│   ├── 1_What_Causes_Merge_Conflicts.md
│   ├── 2_How_to_Detect_Conflicts.md
│   ├── 3_Resolve_Merge_Conflicts.md
│   ├── 4_Best_Practices.md
│   ├── Exercises
│   │   ├── 1_Create_Conflict.md
│   │   ├── 2_Resolve_the_Conflict_Manually.md
│   │   ├── 3_Abort_Merge.md
│   │   ├── 4_Use_VS_Code_Merge_Tool.md
│   │   └── 5_Avoid_Conflicts.md
│   └── README.md
│
├── 6_Project_Structure_for_ML
│   └── README.md
│
├── 7_Project_Management
│   └── README.md
│
├── resources
│   ├── Cheat_Sheet.md
│   ├── Glossary.md
│   └── External_Links.md
│
├── assets
└── README.md

````

---

## Lesson Roadmap

| Lesson | Topic | Description |
|:--|:--|:--|
| **1** | Introduction | Setup Git, configure user identity, and make your first commit |
| **2** | Basic Concepts & Commands | Learn Git’s core workflow, history, and undo commands |
| **3** | Branches | Create, switch, merge, and rebase branches |
| **4** | Remote Repositories | Work with GitHub/GitLab remotes, push/pull/fetch |
| **5** | Conflict Resolution | Detect and resolve merge conflicts |
| **6** | Project Structure | Learn how to organize project directories and files |
| **7** | Project Management | Track tasks and issues directly from Git |

---

## Resources

| File | Purpose |
|------|----------|
| [`resources/Cheat_Sheet.md`](resources/Cheat_Sheet.md) | Quick reference for common Git commands |
| [`resources/Glossary.md`](resources/Glossary.md) | Definitions of key Git terminology |
| [`resources/External_Links.md`](resources/External_Links.md) | Curated list of tutorials, books, and tools |

---

## Prerequisites

Before starting:
- Basic command-line knowledge
- Installed **Git ≥ 2.30**
- A GitHub account (optional, for remote exercises)

---

## How to Use This Repository

1. Clone this repo:
  ```bash
   git clone <repo-url>
   cd git-fundamentals-course
  ```

2. Start from the **1_Introduction** folder and follow each README sequentially.
3. Complete the exercises in each `Exercises/` subfolder.
4. Use `resources/` for quick references.
5. Practice commands locally or with a GitHub test repository.

---

## Learning Outcomes

After completing this course, you will be able to:

* Use Git confidently in solo and team projects
* Work with branches, merges, and remotes
* Resolve conflicts effectively
* Structure and manage real-world software projects
* Contribute to open-source projects with best practices

---

## Feedback & Contributions

Contributions and feedback are welcome!
If you find typos, unclear instructions, or have suggestions, open an issue or pull request.

---

**Author:** _Pouria Mirebrahimi_  
**License:** _MIT_  
**Version:** _1.0.0_