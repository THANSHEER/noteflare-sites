---
title: git_grep
---

# git grep

> Search code within your repository.

---

## 🔍 Basic Search

### Search in Working Directory

```bash
git grep "search term"
```

> Searches tracked files for term.

---

### Case Insensitive

```bash
git grep -i "search"
```

> Ignores case.

---

### Show Line Numbers

```bash
git grep -n "search"
```

> Shows line numbers with results.

---

### Show Only Filenames

```bash
git grep -l "search"
```

> Lists only matching files.

---

### Count Matches

```bash
git grep -c "search"
```

> Shows count of matches per file.

---

## 🎯 Pattern Matching

### Regex Search

```bash
git grep -e "pattern.*match"
```

> Uses regex pattern.

---

### Extended Regex

```bash
git grep -E "pattern|alternative"
```

> Extended regex (OR patterns).

---

### Word Match

```bash
git grep -w "function"
```

> Matches whole word only.

---

## 📁 Limit Scope

### Search Specific Files

```bash
git grep "search" -- "*.js"
```

> Only searches JavaScript files.

---

### Search Directory

```bash
git grep "search" -- src/
```

> Only searches in src/ directory.

---

### Exclude Path

```bash
git grep "search" -- ':!node_modules'
```

> Excludes node_modules.

---

## ⏰ Search History

### Search at Commit

```bash
git grep "search" abc1234
```

> Searches in specific commit.

---

### Search Across Branches

```bash
git grep "search" main develop feature
```

> Searches in multiple branches.

---

### Search All Branches

```bash
git grep "search" $(git rev-list --all)
```

> Searches entire history.

---

## 📊 Output Options

### Show Context

```bash
git grep -C 3 "search"
```

> Shows 3 lines context around matches.

---

### Before Context

```bash
git grep -B 2 "search"
```

> Shows 2 lines before match.

---

### After Context

```bash
git grep -A 2 "search"
```

> Shows 2 lines after match.

---

## 🔗 AND/OR Search

### Match Multiple Terms

```bash
git grep -e "term1" --and -e "term2"
```

> Both terms must appear in same file.

---

### Match Either Term

```bash
git grep -e "term1" --or -e "term2"
```

> Either term matches.

---

### Complex Boolean

```bash
git grep -e "term1" --and \( -e "term2" --or -e "term3" \)
```

> Complex pattern matching.

---

## 💡 Tips

> [!tip] vs Regular grep
> `git grep` is faster because it only searches tracked files.

> [!tip] Find Function Definition
>
> ```bash
> git grep -n "function searchName"
> ```

> [!tip] Find TODO Comments
>
> ```bash
> git grep -n "TODO:"
> ```

---

## 🔗 Related

- [[git_bisect|Bisect]]
- [[../07_Git_Internals/git_detailed_history|History Search]]

---

#git #grep #search #advanced
