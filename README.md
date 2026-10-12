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

## Available Actions

### 1. Setup Project (`./node-setup-project`)

Sets up the Node.js environment using a specified version and restores or installs project dependencies cleanly
(`npm ci`) using `package-lock.json` hashes.

#### Features

- Configures Node.js using `actions/setup-node`.
- Caches `node_modules` based on `package-lock.json` hash.
- Runs `npm ci` only if dependencies are missing or modified.
- Dynamic Node.js version parameter with a default fallback.

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

## 🏗️ Installation

```bash
# Example

```

[//]: # (## 🚀 Using)

[//]: # ()
[//]: # (Check out the [vbetsch/lib-config-ts-test]&#40;https://github.com/vbetsch/lib-config-ts-test&#41; repository for a live)

[//]: # (integration example.)

## 🤝 Contributing

Contributions are welcome! To get started, please ensure you have an approved issue before submitting a PR.

[© 2026 vbetsch — MIT License](LICENSE)
