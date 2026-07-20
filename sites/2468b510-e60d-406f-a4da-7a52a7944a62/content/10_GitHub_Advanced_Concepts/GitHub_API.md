---
title: GitHub_API
---

# GitHub API

> Interact with GitHub programmatically.

---

## 🔧 Using gh CLI

### REST API Call

```bash
gh api repos/{owner}/{repo}
```

> Gets repository info.

---

### Get User Info

```bash
gh api user
```

> Gets authenticated user info.

---

### POST Request

```bash
gh api repos/{owner}/{repo}/issues -X POST -f title="Bug" -f body="Description"
```

> Creates an issue.

---

### With JSON Body

```bash
gh api repos/{owner}/{repo}/labels -X POST \
  --input - <<< '{"name":"urgent","color":"ff0000"}'
```

> Creates label with JSON body.

---

## 🔷 GraphQL

### Basic Query

```bash
gh api graphql -f query='{ viewer { login } }'
```

> Gets your username.

---

### Get Repository Info

```bash
gh api graphql -f query='
  query {
    repository(owner: "owner", name: "repo") {
      name
      description
      stargazerCount
    }
  }
'
```

> Gets repository details.

---

### With Variables

```bash
gh api graphql -f query='
  query($owner: String!, $name: String!) {
    repository(owner: $owner, name: $name) {
      name
    }
  }
' -f owner="octocat" -f name="Hello-World"
```

> Uses query variables.

---

## 🐍 Python

### Install PyGithub

```bash
pip install PyGithub
```

> Install GitHub library.

---

### Python Example

```python
from github import Github

g = Github("YOUR_TOKEN")
repo = g.get_repo("owner/repo")

# List issues
for issue in repo.get_issues():
    print(issue.title)

# Create issue
repo.create_issue(title="Bug", body="Description")
```

> Python GitHub API usage.

---

## 📦 JavaScript

### Install Octokit

```bash
npm install @octokit/rest
```

> Install Octokit.

---

### JavaScript Example

```javascript
import { Octokit } from "@octokit/rest";

const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

// Get repo
const { data: repo } = await octokit.repos.get({
  owner: "owner",
  repo: "repo",
});

// Create issue
await octokit.issues.create({
  owner: "owner",
  repo: "repo",
  title: "Bug",
  body: "Description",
});
```

> JavaScript API usage.

---

## 🔐 Authentication

### Personal Access Token

1. Go to Settings → Developer settings
2. Personal access tokens → Tokens (classic)
3. Generate new token with needed scopes

---

### Use Token with gh

```bash
gh auth login --with-token < token.txt
```

> Authenticates with token.

---

## 💡 Tips

> [!tip] Rate Limits
> REST: 5000 req/hour
> GraphQL: 5000 points/hour

> [!tip] Pagination
>
> ```bash
> gh api repos/{owner}/{repo}/issues --paginate
> ```

---

## 🔗 Related

- [[../09_GitHub_Commands_and_Features/Using_GitHub_CLI|GitHub CLI]]
- [[GitHub_Actions_and_Pipelines|Actions]]

---

#github #api #rest #graphql
