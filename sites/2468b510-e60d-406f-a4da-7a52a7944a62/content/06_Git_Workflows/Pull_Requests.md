---
title: Pull_Requests
---

# Pull Requests

> Propose, review, and merge code changes.

---

## 📊 PR Workflow

```mermaid
graph LR
    A[Branch] --> B[Push]
    B --> C[Create PR]
    C --> D[Review]
    D --> E[Approval]
    E --> F[Merge]
    F --> G[Delete Branch]
```

---

## ➕ Creating PRs

### Create PR (Interactive)

```bash
gh pr create
```

> Interactive PR creation.

---

### Create with Title and Body

```bash
gh pr create --title "Add login feature" --body "Description here"
```

> Creates PR with specified title and description.

---

### Create Draft PR

```bash
gh pr create --draft
```

> Creates draft for early feedback.

---

### Create from Web

```bash
gh pr create --web
```

> Opens browser to create PR.

---

### Auto-fill from Commits

```bash
gh pr create --fill
```

> Uses commit messages for title/body.

---

## 📋 View PRs

### List Your PRs

```bash
gh pr list
```

> Shows open PRs.

---

### List All PRs

```bash
gh pr list --state all
```

> Shows all PRs including closed.

---

### View Specific PR

```bash
gh pr view 123
```

> Shows details of PR #123.

---

### View in Browser

```bash
gh pr view 123 --web
```

> Opens PR in browser.

---

### Check PR Status

```bash
gh pr status
```

> Shows status of relevant PRs.

---

## 🔍 Review PRs

### Checkout PR Locally

```bash
gh pr checkout 123
```

> Checks out PR branch locally.

---

### View PR Diff

```bash
gh pr diff 123
```

> Shows diff of PR changes.

---

### Approve PR

```bash
gh pr review 123 --approve
```

> Approves the PR.

---

### Request Changes

```bash
gh pr review 123 --request-changes --body "Please fix X"
```

> Requests changes before merge.

---

### Comment on PR

```bash
gh pr review 123 --comment --body "LGTM!"
```

> Adds comment without approval.

---

## 🔀 Merge PRs

### Merge with Merge Commit

```bash
gh pr merge 123 --merge
```

> Creates merge commit.

---

### Squash and Merge

```bash
gh pr merge 123 --squash
```

> Squashes all commits into one.

---

### Rebase and Merge

```bash
gh pr merge 123 --rebase
```

> Rebases commits onto base.

---

### Auto-merge When Checks Pass

```bash
gh pr merge 123 --auto --squash
```

> Merges automatically when CI passes.

---

### Delete Branch After Merge

```bash
gh pr merge 123 --squash --delete-branch
```

> Merges and deletes branch.

---

## 📝 Update PRs

### Edit PR Title

```bash
gh pr edit 123 --title "New title"
```

> Changes PR title.

---

### Add Reviewers

```bash
gh pr edit 123 --add-reviewer username
```

> Adds reviewer.

---

### Add Labels

```bash
gh pr edit 123 --add-label "bug"
```

> Adds label.

---

### Mark Ready for Review

```bash
gh pr ready 123
```

> Converts draft to ready.

---

## ❌ Close/Reopen

### Close PR

```bash
gh pr close 123
```

> Closes without merging.

---

### Reopen PR

```bash
gh pr reopen 123
```

> Reopens closed PR.

---

## 📊 PR Template

Create `.github/PULL_REQUEST_TEMPLATE.md`:

```markdown
## Description

Brief description of changes

## Type of Change

- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change

## Testing

How was this tested?

## Checklist

- [ ] Tests pass
- [ ] Docs updated
```

---

## 💡 Tips

> [!tip] Small PRs
> Keep PRs under 400 lines for better reviews.

> [!tip] Link Issues
> Use "Fixes #123" in PR body to auto-close issues.

---

## 🔗 Related

- [[GitHub_Flow|GitHub Flow]]
- [[../10_GitHub_Advanced_Concepts/Code_Reviews_and_Approvals|Code Reviews]]
- [[Forking_Workflow|Forking Workflow]]

---

#git #github #pr #pullrequest #review
