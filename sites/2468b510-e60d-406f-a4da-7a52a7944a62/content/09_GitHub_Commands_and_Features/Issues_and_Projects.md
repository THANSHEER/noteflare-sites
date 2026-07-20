---
title: Issues_and_Projects
---

# Issues and Projects

> Track work with issues and organize with projects.

---

## 📝 Issues

### Create Issue

```bash
gh issue create --title "Bug: Login fails" --body "Description here"
```

> Creates new issue.

---

### Create Issue Interactively

```bash
gh issue create
```

> Interactive issue creation.

---

### Create with Labels

```bash
gh issue create --title "Add feature" --label "enhancement,priority:high"
```

> Creates with labels.

---

### Create with Assignee

```bash
gh issue create --title "Fix bug" --assignee "@me"
```

> Creates and assigns to yourself.

---

## 📋 View Issues

### List Open Issues

```bash
gh issue list
```

> Shows open issues.

---

### List All Issues

```bash
gh issue list --state all
```

> Shows all issues including closed.

---

### List Assigned to You

```bash
gh issue list --assignee "@me"
```

> Your assigned issues.

---

### List by Label

```bash
gh issue list --label bug
```

> Filter by label.

---

### View Specific Issue

```bash
gh issue view 123
```

> Shows issue #123 details.

---

### View in Browser

```bash
gh issue view 123 --web
```

> Opens issue in browser.

---

## ✏️ Edit Issues

### Close Issue

```bash
gh issue close 123
```

> Closes issue #123.

---

### Reopen Issue

```bash
gh issue reopen 123
```

> Reopens closed issue.

---

### Add Comment

```bash
gh issue comment 123 --body "Working on this"
```

> Adds comment to issue.

---

### Add Labels

```bash
gh issue edit 123 --add-label "bug"
```

> Adds label to issue.

---

### Assign Issue

```bash
gh issue edit 123 --add-assignee username
```

> Assigns someone to issue.

---

### Set Milestone

```bash
gh issue edit 123 --milestone "v1.0"
```

> Adds issue to milestone.

---

## 📊 Projects

### List Projects

```bash
gh project list
```

> Shows your projects.

---

### View Project

```bash
gh project view 1
```

> Shows project details.

---

### Create Project

```bash
gh project create --title "Sprint 1" --owner @me
```

> Creates new project.

---

### Add Issue to Project

```bash
gh project item-add 1 --owner @me --url <issue-url>
```

> Adds issue to project.

---

## 📋 Issue Templates

Create `.github/ISSUE_TEMPLATE/bug_report.md`:

```markdown
---
name: Bug Report
about: Report a bug
labels: bug
---

## Description

A clear description of the bug.

## Steps to Reproduce

1. Go to...
2. Click...
3. See error

## Expected Behavior

What should happen.

## Screenshots

If applicable.
```

---

## 💡 Tips

> [!tip] Link PRs to Issues
> Use "Fixes #123" in PR to auto-close issue.

> [!tip] Issue Forms
> Use YAML for structured issue forms.

---

## 🔗 Related

- [[../06_Git_Workflows/Pull_Requests|Pull Requests]]
- [[Using_GitHub_CLI|GitHub CLI]]

---

#github #issues #projects #tracking
