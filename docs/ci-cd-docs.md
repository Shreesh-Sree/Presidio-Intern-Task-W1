# Continuous Integration & Continuous Delivery (CI/CD)

This document explains the CI/CD setup for `DevInsight-Lab` that ensures automated validation gates.

## 1. Automated Validation Flow
To prevent broken code from landing on `main`, every Pull Request triggers a GitHub Actions workflow:
- **Lint Checks**: Checks code formatting and styling guidelines (e.g. using `flake8` or `black` for Python files).
- **Syntax Verification**: Performs compilation checks (e.g., using `python -m py_compile`).
- **Structure Validation**: Validates that required folders and document files exist in the tree.

---

## 2. GitHub Actions Workflow Configuration
A sample workflow configuration is saved under `.github/workflows/ci.yml`:
```yaml
name: CI Verification

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'

      - name: Syntax Check
        run: |
          python -m py_compile $(find . -name "*.py")
```

---

## 3. Merge Gates & Security
- **Branch Protection Rules**: Direct pushes to `main` are restricted. All merges must happen via Pull Requests.
- **Required Status Checks**: The CI build must pass successfully before a PR can be merged.
- **Reviews**: At least one approved review is recommended before merging.
