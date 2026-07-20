---
title: Creating_and_Managing_GitHub_Repos
---

# Creating and Managing GitHub Repos

> Create and configure repositories on GitHub.

---

## ➕ Create Repository

### Create via CLI

```bash
gh repo create my-project --public
```

> Creates public repository.

---

### Create Private

```bash
gh repo create my-project --private
```

> Creates private repository.

---

### Create with Description

```bash
gh repo create my-project --description "Project description" --public
```

> Creates repo with description.

---

### Create with Clone

```bash
gh repo create my-project --public --clone
```

> Creates and clones locally.

---

### Create from Template

```bash
gh repo create my-project --template owner/template-repo
```

> Creates from template repository.

---

### Create in Organization

```bash
gh repo create my-org/my-project --public
```

> Creates repo in organization.

---

## 📋 View Repositories

### List Your Repos

```bash
gh repo list
```

> Shows your repositories.

---

### List with Details

```bash
gh repo list --limit 50
```

> Lists up to 50 repos.

---

### View Repo Info

```bash
gh repo view owner/repo
```

> Shows repository details.

---

### View in Browser

```bash
gh repo view --web
```

> Opens current repo in browser.

---

## ✏️ Edit Repository

### Edit Description

```bash
gh repo edit --description "New description"
```

> Updates repo description.

---

### Edit Homepage

```bash
gh repo edit --homepage "https://example.com"
```

> Sets repository homepage.

---

### Change Visibility

```bash
gh repo edit --visibility private
```

> Makes repository private.

---

### Enable/Disable Features

```bash
gh repo edit --enable-wiki=false
```

> Disables wiki.

```bash
gh repo edit --enable-issues=true
```

> Enables issues.

---

## 🔄 Clone/Fork

### Clone Repository

```bash
gh repo clone owner/repo
```

> Clones to local machine.

---

### Fork Repository

```bash
gh repo fork owner/repo
```

> Creates fork on your account.

---

### Fork and Clone

```bash
gh repo fork owner/repo --clone
```

> Forks and clones.

---

## 🔧 Repository Settings

### Rename Repo

```bash
gh repo rename new-name
```

> Renames repository.

---

### Archive Repo

```bash
gh repo archive owner/repo
```

> Archives repository (read-only).

---

### Delete Repo

```bash
gh repo delete owner/repo --yes
```

> ⚠️ Permanently deletes repository.

---

## 📁 Topics/Tags

### Add Topics

```bash
gh api repos/{owner}/{repo}/topics -X PUT \
  -H "Accept: application/vnd.github.v3+json" \
  -f names='["javascript","react","frontend"]'
```

> Adds topics to repository.

---

## 💡 Tips

> [!tip] Initialize with Files
> Use `--gitignore node` and `--license mit` when creating.

> [!tip] Template Repos
> Mark repo as template in settings for quick project starts.

---

## 🔗 Related

- [[Using_GitHub_CLI|GitHub CLI]]
- [[GitHub_Actions|GitHub Actions]]

---

#github #repo #create #manage
