# CI/CD Workflow with Git

## Continuous Integration

1. Automatically run tests and linters on each push or pull request using tools like:
   - **GitHub Actions**
   - **GitLab CI/CD**
   - **CircleCI**

## Continuous Delivery

1. Deploy changes to a staging environment for testing.
2. Merge to `main` to trigger deployment to production.

## Example GitHub Actions Workflow

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - development
  pull_request:
    branches:
      - development

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Install dependencies
      run: npm install
    - name: Run tests
      run: npm test
```
