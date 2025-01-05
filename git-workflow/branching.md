# Git Branching Strategies

## Branch Structure

- **`main`**: Stable branch for releases.
- **`development`**: Main branch for integrating development.
- **`feature/*`**: Temporary branches for new tasks.
- **`release/*`**: Branches for preparing releases.
- **`hotfix/*`**: Branches for fixing urgent issues.

## Starting Work

### Example (Alice):
```bash
git checkout development
git pull origin development
git checkout -b feature/add-login-form
```

### Example (Bob):
```bash
git checkout development
git pull origin development
git checkout -b feature/add-signup-form
```
