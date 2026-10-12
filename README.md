# lib-config-ts

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

⚙️ A collection of reusable, composite GitHub Actions to standardize CI/CD workflows across Node.js projects.

## 🧩 Structure

Actions are organized in dedicated subdirectories. To keep workflows clean and maintainable, each action maintains its
own scope and input arguments.

```text
.
├── node-setup-project/
│   └── action.yml      # Node.js environment setup & dependency caching
```

## 🚀 Available Actions

### 1. Setup Project (`./node-setup-project`)

Sets up the Node.js environment using a specified version and restores or installs project dependencies cleanly
(`npm ci`) using `package-lock.json` hashes.

#### Features

- Configures Node.js using `actions/setup-node`.
- Caches `node_modules` based on `package-lock.json` hash.
- Runs `npm ci` only if dependencies are missing or modified.
- Dynamic Node.js version parameter.

#### Inputs

| Input          | Description                       | Required | Default |
|:---------------|:----------------------------------|:--------:|:-------:|
| `node-version` | The version of Node.js to set up. |  `true`  |  None   |

#### Usage Example

In your target project's workflow file (`.github/workflows/ci.yml`):

```yaml
name: CI

on:
  push:
    branches: [ main ]
  pull_request:

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Project
        uses: vbetsch/lib-github-actions/node-setup-project@v1
        with:
          node-version: '24.21.0'

      - name: Run Tests
        run: npm test
```

## 📌 Versioning Strategy

This repository follows Semantic Versioning (`vX.Y.Z`).

- **Major Releases (`@v1`)**: Recommended for pipeline stability. Points to the latest backwards-compatible release in
  the `v1.x.x` series.
- **Specific Versions (`@v1.0.0`)**: Use when strict pinning is needed.

### Creating a New Release

```bash
git tag -a v1.0.0 -m "Release v1.0.0"
git tag -fa v1 -m "Update v1 major tag"
git push origin --tags --force
```

## 🛠️ Contributing / Adding New Actions

1. Create a new directory for the action: `mkdir my-new-action`.
2. Add an `action.yml` inside `my-new-action/`.
3. Document the new action in this `README.md`.
4. Tag a new release or update existing release tags.

[© 2026 vbetsch — MIT License](LICENSE)
