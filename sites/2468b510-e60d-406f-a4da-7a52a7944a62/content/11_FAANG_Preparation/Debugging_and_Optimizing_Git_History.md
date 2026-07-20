---
title: Debugging_and_Optimizing_Git_History
---

# Debugging and Optimizing Git History

> Find bugs and clean up history.

---

## 🔍 git bisect

### Start Bisect

```bash
git bisect start
```

> Begins binary search.

```bash
git bisect bad
```

> Current commit is broken.

```bash
git bisect good v1.0.0
```

> This version worked.

---

### Test and Mark

```bash
git bisect good
```

> This commit works.

```bash
git bisect bad
```

> This commit is broken.

---

### Finish

```bash
git bisect reset
```

> Returns to original state.

---

### Automate

```bash
git bisect run npm test
```

> Automatically bisects using test command.

---

## 👤 git blame

### Find Author of Lines

```bash
git blame filename.txt
```

> Shows who wrote each line.

---

### Specific Lines

```bash
git blame -L 10,20 filename.txt
```

> Blame lines 10-20 only.

---

### Ignore Whitespace

```bash
git blame -w filename.txt
```

> Ignores formatting changes.

---

### Show Email

```bash
git blame -e filename.txt
```

> Shows email instead of name.

---

## 📜 Log Search

### Find by Code

```bash
git log -S "functionName"
```

> Finds commits adding/removing this code.

---

### Find by Message

```bash
git log --grep="fix"
```

> Finds commits with "fix" in message.

---

### Find by File Change

```bash
git log -- path/to/file.txt
```

> History of specific file.

---

## 🔄 Interactive Rebase

### Clean Last 5 Commits

```bash
git rebase -i HEAD~5
```

> Opens editor to modify commits.

Options:

- `pick` - keep
- `reword` - change message
- `squash` - combine with previous
- `drop` - remove

---

### Squash All Into One

```bash
git rebase -i --root
```

> Rebases from first commit.

---

## ✏️ Amend Commits

### Fix Last Commit Message

```bash
git commit --amend -m "Corrected message"
```

> Changes last commit message.

---

### Add Files to Last Commit

```bash
git add forgotten-file.txt
```

> Stage forgotten file.

```bash
git commit --amend --no-edit
```

> Add to last commit.

---

## 🧹 History Optimization

### Garbage Collect

```bash
git gc
```

> Cleans up and compresses.

---

### Aggressive Cleanup

```bash
git gc --aggressive
```

> Thorough optimization.

---

### Prune Unreachable

```bash
git prune
```

> Removes unreachable objects.

---

## 💡 Tips

> [!tip] Find Deleted Code
>
> ```bash
> git log -S "deleted_function" --all
> ```

> [!tip] Who Deleted a Line
>
> ```bash
> git log -p -- filename | grep -B 5 "deleted text"
> ```

---

## 🔗 Related

- [[../08_Git_Advanced_Topics/git_bisect|git bisect]]
- [[../08_Git_Advanced_Topics/git_reflog|git reflog]]

---

#git #debug #history #optimize
