---
title: Useful_Git_Snippets
---

# Useful Git Snippets

> Copy-paste solutions for common tasks.

---

## 🔙 Undo Operations

### Undo Last Commit (Keep Changes)

```bash
git reset HEAD~1
```

> Uncommits but keeps file changes.

---

### Undo Last Commit (Discard All)

```bash
git reset --hard HEAD~1
```

> ⚠️ Permanently discards last commit.

---

### Undo Pushed Commit

```bash
git revert HEAD
```

> Creates new commit undoing changes.

---

### Discard All Local Changes

```bash
git checkout -- .
```

> Reverts all files to last commit.

---

### Discard Specific File Changes

```bash
git checkout -- filename.txt
```

> Reverts specific file.

---

## 🌿 Branch Operations

### Delete Local Branch

```bash
git branch -d branch-name
```

> Deletes if merged.

---

### Force Delete Branch

```bash
git branch -D branch-name
```

> Deletes even if unmerged.

---

### Delete Remote Branch

```bash
git push origin --delete branch-name
```

> Removes from remote.

---

### Rename Current Branch

```bash
git branch -m new-name
```

> Renames local branch.

---

### Delete All Merged Branches

```bash
git branch --merged | grep -v "main\|master" | xargs git branch -d
```

> Cleans up merged branches.

---

## 📝 Commit Fixes

### Change Last Commit Message

```bash
git commit --amend -m "New message"
```

> Updates commit message.

---

### Add File to Last Commit

```bash
git add forgotten-file.txt && git commit --amend --no-edit
```

> Adds file without changing message.

---

### Squash Last N Commits

```bash
git rebase -i HEAD~3
```

> Opens editor to squash 3 commits.

---

## 🔍 Find Things

### Find Commit That Introduced Bug

```bash
git bisect start && git bisect bad && git bisect good v1.0
```

> Binary search for bug.

---

### Find Who Changed a Line

```bash
git blame filename.txt
```

> Shows author of each line.

---

### Search for String in Code

```bash
git grep "searchTerm"
```

> Finds in tracked files.

---

### Find Commits by Message

```bash
git log --grep="keyword"
```

> Searches commit messages.

---

### Find Deleted File

```bash
git log --all --full-history -- "**/filename.*"
```

> Locates when file was deleted.

---

## 🧹 Cleanup

### Remove Untracked Files

```bash
git clean -fd
```

> Deletes untracked files and directories.

---

### Prune Remote Branches

```bash
git fetch --prune
```

> Removes stale remote-tracking branches.

---

### Garbage Collect

```bash
git gc --prune=now
```

> Cleans up and optimizes.

---

## 📤 Stash Operations

### Stash with Message

```bash
git stash push -m "Work in progress"
```

> Saves with description.

---

### Apply Specific Stash

```bash
git stash apply stash@{2}
```

> Applies stash by index.

---

### Create Branch from Stash

```bash
git stash branch new-branch
```

> Makes branch from stash.

---

## 🔧 Configuration

### Show All Config

```bash
git config --list --show-origin
```

> Shows config with file sources.

---

### Create Alias

```bash
git config --global alias.st status
```

> Now `git st` = `git status`.

---

### Set Pull Rebase

```bash
git config --global pull.rebase true
```

> Always rebase on pull.

---

## 💡 Tips

> [!tip] Bookmark This Page
> Reference these snippets when needed.

> [!tip] Practice in Test Repo
> Try dangerous commands in a test repo first.

---

## 🔗 Related

- [[Git_Cheat_Sheet|Cheat Sheet]]
- [[Git_Resources|Resources]]

---

#git #snippets #reference #solutions
