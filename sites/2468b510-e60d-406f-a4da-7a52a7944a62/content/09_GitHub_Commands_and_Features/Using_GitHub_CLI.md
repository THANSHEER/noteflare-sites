---
title: Using_GitHub_CLI
---

# Using GitHub CLI

> Command-line interface for GitHub.

---

## 📥 Installation

### macOS (Homebrew)

```bash
brew install gh
```

> Install via Homebrew.

---

### Windows (Winget)

```bash
winget install --id GitHub.cli
```

> Install via Windows Package Manager.

---

### Linux (Debian/Ubuntu)

```bash
sudo apt install gh
```

> Install via apt.

---

## 🔐 Authentication

### Login

```bash
gh auth login
```

> Interactive login to GitHub.

---

### Login with Token

```bash
gh auth login --with-token < token.txt
```

> Login using personal access token.

---

### Check Status

```bash
gh auth status
```

> Shows authentication status.

---

### Logout

```bash
gh auth logout
```

> Logs out of GitHub CLI.

---

## 📁 Repository Commands

### Clone

```bash
gh repo clone owner/repo
```

> Clones repository.

---

### Create

```bash
gh repo create my-repo --public
```

> Creates new repository.

---

### Fork

```bash
gh repo fork owner/repo --clone
```

> Forks and clones.

---

### View

```bash
gh repo view
```

> Shows current repo info.

---

## 🔄 Pull Request Commands

### Create PR

```bash
gh pr create
```

> Creates pull request.

---

### List PRs

```bash
gh pr list
```

> Shows open PRs.

---

### Checkout PR

```bash
gh pr checkout 123
```

> Checks out PR locally.

---

### View PR

```bash
gh pr view 123
```

> Shows PR details.

---

### Merge PR

```bash
gh pr merge 123 --squash
```

> Squash merges PR.

---

### Review PR

```bash
gh pr review 123 --approve
```

> Approves PR.

---

## 📝 Issue Commands

### Create Issue

```bash
gh issue create --title "Bug" --body "Description"
```

> Creates issue.

---

### List Issues

```bash
gh issue list
```

> Shows open issues.

---

### Close Issue

```bash
gh issue close 123
```

> Closes issue.

---

## 🔧 Workflow Commands

### List Workflows

```bash
gh workflow list
```

> Shows all workflows.

---

### Run Workflow

```bash
gh workflow run ci.yml
```

> Triggers workflow.

---

### View Runs

```bash
gh run list
```

> Shows workflow runs.

---

### Watch Run

```bash
gh run watch
```

> Live-watch running workflow.

---

## 🔍 API Access

### REST API Call

```bash
gh api repos/{owner}/{repo}
```

> Makes API request.

---

### GraphQL Query

```bash
gh api graphql -f query='{ viewer { login } }'
```

> Makes GraphQL query.

---

## ⚙️ Configuration

### Set Editor

```bash
gh config set editor "code --wait"
```

> Sets default editor.

---

### Set Protocol

```bash
gh config set git_protocol ssh
```

> Uses SSH for cloning.

---

### View Config

```bash
gh config list
```

> Shows configuration.

---

## 💡 Tips

> [!tip] Aliases
>
> ```bash
> gh alias set co 'pr checkout'
> ```
>
> Create shortcuts.

> [!tip] JSON Output
>
> ```bash
> gh issue list --json number,title
> ```
>
> Get JSON for scripting.

---

## 🔗 Related

- [[Creating_and_Managing_GitHub_Repos|Manage Repos]]
- [[GitHub_Actions|Actions]]

---

#github #cli #gh #commands
