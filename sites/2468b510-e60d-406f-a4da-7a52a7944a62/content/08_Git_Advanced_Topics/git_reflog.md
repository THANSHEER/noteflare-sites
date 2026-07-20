---
title: git_reflog
---

# git reflog

> Safety net for recovering lost work.

---

## 📊 What is Reflog?

Reflog tracks every HEAD movement:

- Commits
- Checkouts
- Resets
- Rebases
- Merges

```mermaid
graph LR
    A[Every HEAD change] --> B[Recorded in reflog]
    B --> C[Can recover lost commits]
```

---

## 📋 View Reflog

### Show Reflog

```bash
git reflog
```

> Shows HEAD history.

Output:

```
abc1234 HEAD@{0}: commit: Message
def5678 HEAD@{1}: checkout: moving from main to feature
ghi9012 HEAD@{2}: commit: Previous message
```

---

### Detailed View

```bash
git reflog show HEAD
```

> Same as `git reflog`.

---

### Branch Reflog

```bash
git reflog show main
```

> Shows history for specific branch.

---

### With Dates

```bash
git reflog --date=relative
```

> Shows relative dates.

---

### With Full Dates

```bash
git reflog --date=iso
```

> Shows ISO format dates.

---

## 🔄 Recover Lost Commits

### After Hard Reset

```bash
git reset --hard HEAD~3
# Oops! Need those commits back!
```

---

### Find Lost Commit

```bash
git reflog
```

> Find the hash of lost commit.

---

### Recover Commit

```bash
git reset --hard abc1234
```

> Reset to the lost commit.

---

### Create Branch from Lost Commit

```bash
git branch recovered abc1234
```

> Creates branch at lost commit.

---

## 🌿 Recover Deleted Branch

### After Deleting Branch

```bash
git branch -D feature-branch
# Need it back!
```

---

### Find Last Commit

```bash
git reflog | grep feature-branch
```

> Find where branch was.

---

### Recreate Branch

```bash
git branch feature-branch abc1234
```

> Recreates branch at that commit.

---

## ⏪ Recover from Bad Rebase

### After Rebase Gone Wrong

```bash
git rebase main
# Made a mess!
```

---

### Find Pre-rebase State

```bash
git reflog
```

> Look for "rebase: starting" or "checkout".

---

### Reset to Pre-rebase

```bash
git reset --hard HEAD@{5}
```

> Returns to state 5 moves ago.

---

## 🧹 Manage Reflog

### Expire Old Entries

```bash
git reflog expire --expire=90.days.ago --all
```

> Removes entries older than 90 days.

---

### Expire All Now

```bash
git reflog expire --expire=now --all
```

> Removes all reflog entries.

---

### Delete Specific Entry

```bash
git reflog delete HEAD@{2}
```

> Deletes specific entry.

---

## ⏰ Reference by Time

### By Relative Time

```bash
git show HEAD@{1.hour.ago}
```

> Shows HEAD from 1 hour ago.

---

### By Date

```bash
git show main@{2024-01-15}
```

> Shows main branch on specific date.

---

### By Yesterday

```bash
git diff main@{yesterday} main
```

> Changes since yesterday.

---

## 💡 Tips

> [!tip] Reflog is Local
> Reflog only exists on your machine. Not shared with remote.

> [!tip] Default Retention
> Entries expire after 90 days (30 for unreachable).

> [!warning] After gc
> After `git gc`, unreachable commits may be deleted.

---

## 🔗 Related

- [[git_bisect|Bisect]]
- [[../03_Advanced_Git_Commands/git_reset_and_checkout|Reset & Checkout]]

---

#git #reflog #recovery #advanced
