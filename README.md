# lib-github-actions

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A collection of reusable, [composite GitHub Actions](https://docs.github.com/en/actions/tutorials/create-actions/create-a-composite-action)
to standardize CI/CD workflows

## 🧩 Structure

Actions are organized in dedicated subdirectories. To keep workflows clean and maintainable, each action maintains its
own scope and input arguments.

### Actions

| Action                                       | Description                                                                                                     | Parameters                                                         |
|----------------------------------------------|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| [`node-setup-project`](./node-setup-project) | Sets up the Node.js environment using a specified version and restores or installs project dependencies cleanly | - **node-version** : The version of Node.js to set up (_required_) |

## 🚀 Using

For example if you want to use `node-setup-project` action, in your target project's workflow file you have to set it
like this :

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
        # use the action with the latest available version
        uses: vbetsch/lib-github-actions/node-setup-project@v1
        # set action parameters
        with:
          node-version: '24.21.0'

      - name: Run Tests
        run: npm test
```

## 🤝 Contributing

1. Create a new directory for the action: `mkdir my-new-action`.
2. Add an `action.yml` inside `my-new-action/`.
3. Document the new action in this `README.md`.
4. Tag a new release or update existing release tags.

[© 2026 vbetsch — MIT License](LICENSE)
