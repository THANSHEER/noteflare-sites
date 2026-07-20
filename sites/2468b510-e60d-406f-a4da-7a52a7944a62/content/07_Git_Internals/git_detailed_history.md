---
title: git_detailed_history
---

# git detailed history

> Advanced history navigation and analysis.

---

## 📜 Log Formats

### One Line

```bash
git log --oneline
```

> Compact: hash + message.

---

### Graph View

```bash
git log --graph --oneline --all
```

> Visual branch structure.

---

### With Diff

```bash
git log -p
```

> Shows patch for each commit.

---

### With Stats

```bash
git log --stat
```

> Shows files changed per commit.

---

## 🔍 Filter by Author

### By Name

```bash
git log --author="John"
```

> Commits by author containing "John".

---

### By Email

```bash
git log --author="john@email.com"
```

> Commits by specific email.

---

## 📅 Filter by Date

### Since Date

```bash
git log --since="2024-01-01"
```

> Commits after date.

---

### Until Date

```bash
git log --until="2024-06-01"
```

> Commits before date.

---

### Relative Date

```bash
git log --since="2 weeks ago"
```

> Commits from last 2 weeks.

---

## 💬 Filter by Message

### By Message Content

```bash
git log --grep="bug fix"
```

> Commits with "bug fix" in message.

---

### Case Insensitive

```bash
git log --grep="bug" -i
```

> Case insensitive search.

---

## 📁 Filter by File

### By Path

```bash
git log -- path/to/file.txt
```

> Commits touching this file.

---

### Follow Renames

```bash
git log --follow -- path/to/file.txt
```

> Tracks file through renames.

---

## 📝 Filter by Code

### By Code Change (Pickaxe)

```bash
git log -S "function_name"
```

> Commits that added/removed this string.

---

### By Regex

```bash
git log -G "pattern.*match"
```

> Commits matching regex pattern.

---

## 👤 git blame

### See Line Authors

```bash
git blame file.txt
```

> Shows who last modified each line.

---

### Specific Lines

```bash
git blame -L 10,20 file.txt
```

> Blame only lines 10-20.

---

### Ignore Whitespace

```bash
git blame -w file.txt
```

> Ignores whitespace changes.

---

## 📊 Statistics

### Commits by Author

```bash
git shortlog -sn
```

> Commit count by author.

---

### With Emails

```bash
git shortlog -sne
```

> Includes email addresses.

---

## 📈 Custom Format

### Format Placeholders

| Placeholder | Meaning       |
| ----------- | ------------- |
| `%H`        | Full hash     |
| `%h`        | Short hash    |
| `%an`       | Author name   |
| `%s`        | Subject       |
| `%ar`       | Relative date |

---

### Custom Format Example

```bash
git log --pretty=format:"%h %an %s"
```

> Short hash, author, subject.

---

### Colored Output

```bash
git log --pretty=format:"%C(yellow)%h%Creset %s"
```

> Yellow hash, normal subject.

---

## 💡 Tips

> [!tip] Create Log Alias
>
> ```bash
> git config --global alias.lg "log --oneline --graph --all"
> ```

> [!tip] Find Deleted Code
>
> ```bash
> git log -S "deleted_code" --all
> ```

---

## 🔗 Related

- [[git_objects|Git Objects]]
- [[git_commits_and_refs|Commits and Refs]]
- [[../02_Basic_Git_Commands/git_log_and_history|Basic Log]]

---

#git #log #history #blame #internals
