---
title: Git_Cheat_Sheet
---

# Git Cheat Sheet

> Quick reference for essential commands.

---

## 🚀 Setup

```bash
git config --global user.name "Name"
```

> Set your name.

```bash
git config --global user.email "email@example.com"
```

> Set your email.

---

## 📁 Create Repository

```bash
git init
```

> Initialize new repo.

```bash
git clone https://github.com/user/repo.git
```

> Clone existing repo.

---

## 📝 Basic Workflow

```bash
git status
```

> Check status.

```bash
git add .
```

> Stage all changes.

```bash
git commit -m "Message"
```

> Commit changes.

```bash
git push
```

> Push to remote.

```bash
git pull
```

> Pull from remote.

---

## 🌿 Branches

```bash
git branch
```

> List branches.

```bash
git checkout -b feature
```

> Create and switch.

```bash
git switch main
```

> Switch branch.

```bash
git merge feature
```

> Merge branch.

```bash
git branch -d feature
```

> Delete branch.

---

## 🔍 View Changes

```bash
git diff
```

> Unstaged changes.

```bash
git diff --staged
```

> Staged changes.

```bash
git log --oneline
```

> Compact history.

---

## ↩️ Undo

```bash
git restore file.txt
```

> Discard changes.

```bash
git restore --staged file.txt
```

> Unstage file.

```bash
git reset HEAD~1
```

> Undo last commit (keep changes).

```bash
git reset --hard HEAD~1
```

> ⚠️ Undo last commit (discard changes).

---

## 💾 Stash

```bash
git stash
```

> Save changes temporarily.

```bash
git stash pop
```

> Restore stashed changes.

```bash
git stash list
```

> List stashes.

---

## 🏷️ Tags

```bash
git tag v1.0.0
```

> Create tag.

```bash
git push --tags
```

> Push tags.

---

## 🔧 Remote

```bash
git remote -v
```

> View remotes.

```bash
git remote add origin url
```

> Add remote.

```bash
git fetch
```

> Download changes (no merge).

---

## 🔀 Rebase

```bash
git rebase main
```

> Rebase onto main.

```bash
git rebase -i HEAD~3
```

> Interactive rebase.

---

## 📊 Quick Reference Table

| Task    | Command                |
| ------- | ---------------------- |
| Init    | `git init`             |
| Clone   | `git clone url`        |
| Add all | `git add .`            |
| Commit  | `git commit -m "msg"`  |
| Push    | `git push`             |
| Pull    | `git pull`             |
| Status  | `git status`           |
| Log     | `git log --oneline`    |
| Branch  | `git checkout -b name` |
| Merge   | `git merge name`       |
| Stash   | `git stash`            |
| Diff    | `git diff`             |

---

## 🔗 Related

- [[Git_Resources|Resources]]
- [[Useful_Git_Snippets|Snippets]]

---

#git #cheatsheet #reference #quick
