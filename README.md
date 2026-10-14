# lib-github-actions

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

⚙️ A collection of reusable, composite GitHub Actions to standardize CI/CD workflows

## 🧩 Structure

Actions are organized in dedicated subdirectories. To keep workflows clean and maintainable, each action maintains its
own scope and input arguments.

```text
.
├── node-setup-project/
│   └── action.yml      # Node.js environment setup & dependency caching
```

### Packages

| Package                                                                              | Description               | Path                                                         | Details                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------|---------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [`@vbetsch/config-eslint`](https://www.npmjs.com/package/@vbetsch/config-eslint)     | Core ESLint configuration | [src/packages/config-eslint](src/packages/config-eslint)     | [![npm package version](https://img.shields.io/npm/v/@vbetsch/config-eslint)](https://www.npmjs.com/package/@vbetsch/config-eslint) [![npm downloads number per week](https://img.shields.io/npm/dw/@vbetsch/config-eslint)](https://www.npmjs.com/package/@vbetsch/config-eslint) [![npm package install size](https://packagephobia.com/badge?p=@vbetsch/config-eslint)](https://www.npmjs.com/package/@vbetsch/config-eslint)             |
| [`@vbetsch/config-jest`](https://www.npmjs.com/package/@vbetsch/config-jest)         | Testing configuration     | [src/packages/config-jest](src/packages/config-jest)         | [![npm package version](https://img.shields.io/npm/v/@vbetsch/config-jest)](https://www.npmjs.com/package/@vbetsch/config-jest) [![npm downloads number per week](https://img.shields.io/npm/dw/@vbetsch/config-jest)](https://www.npmjs.com/package/@vbetsch/config-jest) [![npm package install size](https://packagephobia.com/badge?p=@vbetsch/config-jest)](https://www.npmjs.com/package/@vbetsch/config-jest)                         |
| [`@vbetsch/config-prettier`](https://www.npmjs.com/package/@vbetsch/config-prettier) | Formatting standards      | [src/packages/config-prettier](src/packages/config-prettier) | [![npm package version](https://img.shields.io/npm/v/@vbetsch/config-prettier)](https://www.npmjs.com/package/@vbetsch/config-prettier) [![npm downloads number per week](https://img.shields.io/npm/dw/@vbetsch/config-prettier)](https://www.npmjs.com/package/@vbetsch/config-prettier) [![npm package install size](https://packagephobia.com/badge?p=@vbetsch/config-prettier)](https://www.npmjs.com/package/@vbetsch/config-prettier) |
| [`@vbetsch/config-tsconfig`](https://www.npmjs.com/package/@vbetsch/config-tsconfig) | Compiler settings         | [src/packages/config-tsconfig](src/packages/config-tsconfig) | [![npm package version](https://img.shields.io/npm/v/@vbetsch/config-tsconfig)](https://www.npmjs.com/package/@vbetsch/config-tsconfig) [![npm downloads number per week](https://img.shields.io/npm/dw/@vbetsch/config-tsconfig)](https://www.npmjs.com/package/@vbetsch/config-tsconfig) [![npm package install size](https://packagephobia.com/badge?p=@vbetsch/config-tsconfig)](https://www.npmjs.com/package/@vbetsch/config-tsconfig) |



### Creating a New Release

```bash
git tag -a v1 -m "Release v1"
git tag -fa v1 -m "Update v1 major tag"
git push origin --tags --force
```

## 🛠️ Contributing / Adding New Actions

1. Create a new directory for the action: `mkdir my-new-action`.
2. Add an `action.yml` inside `my-new-action/`.
3. Document the new action in this `README.md`.
4. Tag a new release or update existing release tags.

[© 2026 vbetsch — MIT License](LICENSE)
