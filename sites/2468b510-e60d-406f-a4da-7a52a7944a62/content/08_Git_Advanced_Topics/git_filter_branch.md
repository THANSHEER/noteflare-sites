---
title: git_filter_branch
---

# git filter-branch

> Rewrite Git history (use with caution).

---

## ⚠️ Warning

> [!caution] History Rewriting
> This rewrites history and changes commit hashes. Never use on shared branches.

---

## 🔧 Modern Alternative

### Use git-filter-repo (Recommended)

```bash
pip install git-filter-repo
```

> Install the modern alternative (faster, safer).

---

## ✉️ Change Author Info

### Filter-repo: Change Email

```bash
git filter-repo --email-callback '
    return email.replace(b"old@email.com", b"new@email.com")
'
```

> Changes email throughout history.

---

### Classic: Update Author

```bash
git filter-branch --env-filter '
if [ "$GIT_AUTHOR_EMAIL" = "old@email.com" ]; then
    export GIT_AUTHOR_EMAIL="new@email.com"
fi
' -- --all
```

> Legacy way to change author email.

---

## 🗑️ Remove Files

### Filter-repo: Remove File

```bash
git filter-repo --path secrets.txt --invert-paths
```

> Removes file from entire history.

---

### Remove Folder

```bash
git filter-repo --path config/ --invert-paths
```

> Removes entire folder from history.

---

### BFG Cleaner (Alternative)

```bash
bfg --delete-files secrets.txt
```

> Fast file removal tool.

---

### BFG: Remove Large Files

```bash
bfg --strip-blobs-bigger-than 100M
```

> Removes files larger than 100MB.

---

## 📁 Subdirectory to Root

### Extract Subdirectory

```bash
git filter-repo --subdirectory-filter src/
```

> Makes src/ the new root.

---

## ✏️ Rewrite Messages

### Filter-repo: Replace Text

```bash
git filter-repo --message-callback '
    return message.replace(b"old-text", b"new-text")
'
```

> Replaces text in all commit messages.

---

## 🧹 After Rewriting

### Force Push

```bash
git push --force --all
```

> ⚠️ Push rewritten history.

---

### Push Tags

```bash
git push --force --tags
```

> Push rewritten tags.

---

### Clean Up

```bash
git reflog expire --expire=now --all
```

> Expire old reflog entries.

```bash
git gc --prune=now
```

> Remove old objects.

---

## 📊 Comparison

| Tool          | Speed | Safety | Use Case             |
| ------------- | ----- | ------ | -------------------- |
| filter-repo   | Fast  | Good   | Most cases           |
| BFG           | Fast  | Good   | Remove files/secrets |
| filter-branch | Slow  | ⚠️     | Legacy               |

---

## 💡 Tips

> [!warning] Backup First
>
> ```bash
> git clone --mirror repo backup
> ```

> [!tip] Fresh Clone After
> After rewriting, have team members clone fresh.

---

## 🔗 Related

- [[git_bisect|Bisect]]
- [[git_reflog|Reflog]]

---

#git #filter #history #rewrite #advanced
