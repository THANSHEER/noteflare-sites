---
title: GitHub_Actions_and_Pipelines
---

# GitHub Actions and Pipelines

> Advanced workflow patterns.

---

## 🔄 Reusable Workflows

### Create Reusable Workflow

`.github/workflows/reusable-test.yml`:

```yaml
name: Reusable Test

on:
  workflow_call:
    inputs:
      node-version:
        required: true
        type: string

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ inputs.node-version }}
      - run: npm test
```

---

### Use Reusable Workflow

```yaml
jobs:
  call-tests:
    uses: ./.github/workflows/reusable-test.yml
    with:
      node-version: "20"
```

> Calls reusable workflow.

---

## 📦 Composite Actions

### Create Composite Action

`.github/actions/setup/action.yml`:

```yaml
name: "Setup Project"
description: "Setup Node and install deps"

runs:
  using: "composite"
  steps:
    - uses: actions/setup-node@v4
      with:
        node-version: "20"
    - shell: bash
      run: npm ci
```

---

### Use Composite Action

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: ./.github/actions/setup
  - run: npm test
```

> Uses local composite action.

---

## 🔀 Matrix Builds

### Basic Matrix

```yaml
strategy:
  matrix:
    node: [16, 18, 20]
    os: [ubuntu-latest, windows-latest]
runs-on: ${{ matrix.os }}
steps:
  - uses: actions/setup-node@v4
    with:
      node-version: ${{ matrix.node }}
```

> Runs on multiple versions and OS.

---

### Include/Exclude

```yaml
strategy:
  matrix:
    node: [16, 18, 20]
    os: [ubuntu-latest, windows-latest]
    exclude:
      - node: 16
        os: windows-latest
    include:
      - node: 20
        os: macos-latest
```

> Customizes matrix combinations.

---

## 📊 Job Dependencies

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: npm run build

  test:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - run: npm test

  deploy:
    needs: [build, test]
    runs-on: ubuntu-latest
    steps:
      - run: npm run deploy
```

> Deploy runs after build AND test.

---

## 📤 Artifacts

### Upload Artifact

```yaml
- uses: actions/upload-artifact@v4
  with:
    name: build-output
    path: dist/
```

> Saves build output.

---

### Download Artifact

```yaml
- uses: actions/download-artifact@v4
  with:
    name: build-output
```

> Gets artifact from earlier job.

---

## 🔐 Secrets in Actions

### Use Secrets

```yaml
env:
  API_KEY: ${{ secrets.API_KEY }}
run: |
  npm run deploy
```

> Uses repository secret.

---

## ⏰ Conditional Execution

### If Condition

```yaml
steps:
  - name: Deploy to prod
    if: github.ref == 'refs/heads/main'
    run: npm run deploy-prod
```

> Only runs on main branch.

---

### On Success/Failure

```yaml
- name: Notify on failure
  if: failure()
  run: echo "Build failed!"

- name: Cleanup
  if: always()
  run: npm run cleanup
```

> Runs based on status.

---

## 💡 Tips

> [!tip] Cache Dependencies
>
> ```yaml
> - uses: actions/cache@v4
>   with:
>     path: node_modules
>     key: modules-${{ hashFiles('package-lock.json') }}
> ```

> [!tip] Concurrency
>
> ```yaml
> concurrency:
>   group: ${{ github.workflow }}-${{ github.ref }}
>   cancel-in-progress: true
> ```
>
> Cancels duplicate runs.

---

## 🔗 Related

- [[../09_GitHub_Commands_and_Features/GitHub_Actions|Basic Actions]]
- [[GitHub_CICD|CI/CD]]

---

#github #actions #pipeline #advanced
