---
title: 00_Overview
---

# Git & GitHub - Developer Reference

> A comprehensive guide to Git version control and GitHub collaboration.

---

## 📚 Quick Navigation

| Section                                              | Description                   |
| ---------------------------------------------------- | ----------------------------- |
| [[01_Installation_Setup\|Installation & Setup]]      | Install and configure Git     |
| [[02_Basic_Git_Commands\|Basic Commands]]            | Essential daily commands      |
| [[03_Advanced_Git_Commands\|Advanced Commands]]      | Rebase, stash, submodules     |
| [[04_Branching_and_Merging\|Branching]]              | Branch strategies and merging |
| [[05_Remote_Repositories\|Remote Repos]]             | Work with remote repositories |
| [[06_Git_Workflows\|Workflows]]                      | Git Flow, GitHub Flow, PRs    |
| [[07_Git_Internals\|Internals]]                      | How Git works under the hood  |
| [[08_Git_Advanced_Topics\|Advanced Topics]]          | Bisect, hooks, reflog         |
| [[09_GitHub_Commands_and_Features\|GitHub Features]] | Actions, Issues, CLI          |
| [[10_GitHub_Advanced_Concepts\|GitHub Advanced]]     | CI/CD, API, Secrets           |
| [[11_FAANG_Preparation\|FAANG Prep]]                 | Enterprise workflows          |
| [[12_Reference\|Reference]]                          | Cheat sheet and resources     |

---

## 🚀 Quick Start Commands

### Check Git Version

```bash
git --version
```

> Shows the installed Git version.

---

### Configure Your Identity

```bash
git config --global user.name "Your Name"
```

> Sets your name for all commits.

```bash
git config --global user.email "you@example.com"
```

> Sets your email for all commits.

---

### Initialize a Repository

```bash
git init
```

> Creates a new Git repository in current directory.

---

### Clone a Repository

```bash
git clone https://github.com/user/repo.git
```

> Downloads a repository from GitHub to your computer.

---

### Basic Workflow

```mermaid
graph LR
    A[Edit Files] --> B[git add]
    B --> C[git commit]
    C --> D[git push]
```

---

### Stage All Changes

```bash
git add .
```

> Stages all modified and new files for commit.

---

### Commit Changes

```bash
git commit -m "Your commit message"
```

> Creates a commit with your staged changes.

---

### Push to Remote

```bash
git push
```

> Uploads your commits to the remote repository.

---

### Pull Latest Changes

```bash
git pull
```

> Downloads and merges changes from remote repository.

---

## 📖 Learning Path

### Beginner

1. [[01_Installation_Setup/Installing_Git|Installing Git]]
2. [[01_Installation_Setup/Configuring_Git|Configuring Git]]
3. [[02_Basic_Git_Commands/git_init_and_clone|git init & clone]]
4. [[02_Basic_Git_Commands/git_add_commit|git add & commit]]
5. [[02_Basic_Git_Commands/git_push_and_pull|git push & pull]]

### Intermediate

1. [[04_Branching_and_Merging/Creating_and_Checking_Out_Branches|Branching]]
2. [[04_Branching_and_Merging/Merging_and_Resolving_Conflicts|Merging]]
3. [[03_Advanced_Git_Commands/git_stash|git stash]]
4. [[06_Git_Workflows/Pull_Requests|Pull Requests]]

### Advanced

1. [[03_Advanced_Git_Commands/git_rebase_and_merge|git rebase]]
2. [[07_Git_Internals/git_objects|Git Objects]]
3. [[08_Git_Advanced_Topics/git_hooks|Git Hooks]]
4. [[10_GitHub_Advanced_Concepts/GitHub_CICD|CI/CD]]

---

#git #github #overview #reference

