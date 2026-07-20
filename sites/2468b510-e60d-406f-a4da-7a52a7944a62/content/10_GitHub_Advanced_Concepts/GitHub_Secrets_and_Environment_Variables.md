---
title: GitHub_Secrets_and_Environment_Variables
---

# GitHub Secrets and Environment Variables

> Manage sensitive data in workflows.

---

## 🔐 Types of Secrets

| Type         | Scope         | Where Set            |
| ------------ | ------------- | -------------------- |
| Repository   | Single repo   | Settings → Secrets   |
| Environment  | Specific env  | Environment settings |
| Organization | All org repos | Org settings         |

---

## ➕ Add Secrets

### Add via CLI

```bash
gh secret set API_KEY
```

> Prompts for value interactively.

---

### Add with Value

```bash
gh secret set API_KEY --body "your-api-key-value"
```

> Sets secret directly.

---

### Add from File

```bash
gh secret set API_KEY < key.txt
```

> Sets secret from file.

---

### Add for Environment

```bash
gh secret set API_KEY --env production
```

> Sets secret for specific environment.

---

### Add for Organization

```bash
gh secret set ORG_SECRET --org my-org
```

> Sets organization-level secret.

---

## 📋 List Secrets

### List Repository Secrets

```bash
gh secret list
```

> Shows secret names (not values).

---

### List Environment Secrets

```bash
gh secret list --env production
```

> Shows secrets for environment.

---

## 🗑️ Delete Secrets

### Delete Secret

```bash
gh secret delete API_KEY
```

> Removes secret.

---

### Delete Environment Secret

```bash
gh secret delete API_KEY --env production
```

> Removes environment secret.

---

## 📊 Use Secrets in Workflows

### Environment Variable

```yaml
steps:
  - run: echo "Deploying..."
    env:
      API_KEY: ${{ secrets.API_KEY }}
```

> Sets as environment variable.

---

### In Step Input

```yaml
- uses: some-action@v1
  with:
    api-key: ${{ secrets.API_KEY }}
```

> Passes to action input.

---

### Conditional on Secret

```yaml
- name: Deploy if key exists
  if: ${{ secrets.DEPLOY_KEY != '' }}
  run: deploy
```

> Checks if secret exists.

---

## 🔧 Environment Variables

### Set Repository Variable

```bash
gh variable set NODE_ENV --body "production"
```

> Sets repository variable.

---

### List Variables

```bash
gh variable list
```

> Shows repository variables.

---

### Use Variables in Workflow

```yaml
env:
  NODE_ENV: ${{ vars.NODE_ENV }}
```

> Uses repository variable.

---

## 📁 .env Files

### Use dotenv

```yaml
- name: Load .env
  run: |
    set -a
    source .env
    npm run build
```

> Loads local .env file.

---

## ⚠️ Security Best Practices

### Never Echo Secrets

```yaml
# ❌ BAD - exposes secret
- run: echo ${{ secrets.API_KEY }}

# ✅ GOOD - use in env
- run: ./deploy.sh
  env:
    API_KEY: ${{ secrets.API_KEY }}
```

---

### Mask Custom Values

```yaml
- run: |
    echo "::add-mask::$CUSTOM_SECRET"
```

> Masks value in logs.

---

## 💡 Tips

> [!tip] Secrets are Masked
> GitHub automatically masks known secrets in logs.

> [!warning] Fork PRs
> Secrets aren't available to workflows from forks.

> [!tip] Rotate Secrets
> Regularly update secrets for security.

---

## 🔗 Related

- [[../09_GitHub_Commands_and_Features/GitHub_Actions|GitHub Actions]]
- [[GitHub_CICD|CI/CD]]

---

#github #secrets #environment #security
