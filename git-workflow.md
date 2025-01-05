# Git Workflow for Multiple Developers

## Actors
1. **Alice**: Works on the task `feature/add-login-form`.
2. **Bob**: Works on the task `feature/add-signup-form`.

---

## 1. Branch Structure

- `main`: Stable branch for releases.
- `development`: Main branch for integrating development.
- `feature/*`: Temporary branches for new tasks.
- `release/*`: Branches for preparing releases.
- `hotfix/*`: Branches for fixing urgent issues.

---

## 2. Starting Work

### Alice:
```bash
git checkout development
git pull origin development
git checkout -b feature/add-login-form
```

### Bob:
```bash
git checkout development
git pull origin development
git checkout -b feature/add-signup-form
```

---

## 3. Parallel Work on Tasks

### Alice:
1. Add the login form UI:
   ```bash
   git add .
   git commit -m "feat: add login form ui"
   ```

2. Fix validation bug:
   ```bash
   git add .
   git commit -m "fix: login form validation"
   ```

3. Update styles:
   ```bash
   git add .
   git commit -m "style: apply prettier"
   ```

4. Optimize data handling:
   ```bash
   git add .
   git commit -m "refactor: optimize login form data processing"
   ```

### Bob:
1. Add basic functionality for the signup form:
   ```bash
   git add .
   git commit -m "feat: add basic functionality for the signup form"
   ```

2. Add tests:
   ```bash
   git add .
   git commit -m "test: add tests for signup form validation"
   ```

3. Fix error with empty form submission:
   ```bash
   git add .
   git commit -m "fix: resolve error on empty signup form submission"
   ```

4. Add documentation:
   ```bash
   git add .
   git commit -m "docs: add instructions for using the signup form"
   ```

---

## 4. Syncing with `development` (Rebase)

### Alice:
```bash
git checkout development
git pull origin development
git checkout feature/add-login-form
git rebase development
```

If conflicts arise:
1. Resolve the conflicts manually.
2. After resolving, continue the rebase:
   ```bash
   git rebase --continue
   ```

3. Push the updated branch:
   ```bash
   git push origin feature/add-login-form
   ```

### Bob:
```bash
git checkout development
git pull origin development
git checkout feature/add-signup-form
git rebase development
```

If conflicts arise:
1. Resolve the conflicts manually.
2. After resolving, continue the rebase:
   ```bash
   git rebase --continue
   ```

3. Push the updated branch:
   ```bash
   git push origin feature/add-signup-form
   ```

---

## 5. Pushing Changes

### Alice:
```bash
git push origin feature/add-login-form
```

### Bob:
```bash
git push origin feature/add-signup-form
```

---

## 6. Creating Pull Requests

### Alice:
Create a PR from the branch `feature/add-login-form` to `development` with the following description:
```plaintext
feat: added login functionality

Added a login form with data validation and a basic UI.
Fixed validation errors and optimized data processing logic.
```

### Bob:
Create a PR from the branch `feature/add-signup-form` to `development` with the following description:
```plaintext
feat: added signup functionality

Implemented basic signup form functionality, added tests, and updated documentation.
Resolved issues related to empty form submissions.
```

---

## 7. Merging Pull Requests

Use the **squash and merge** strategy when merging feature branches into `development`.

---

## 8. Creating a Release

### Creating the Release Branch:
```bash
git checkout development
git pull origin development
git checkout -b release/1.0.0
git push origin release/1.0.0
```

### Finalizing the Release:
1. Merge into `main`:
   ```bash
   git checkout main
   git merge --no-ff release/1.0.0
   git commit -m "chore: version 1.0.0"
   git push origin main
   ```

2. Merge into `development`:
   ```bash
   git checkout development
   git merge --no-ff release/1.0.0
   git push origin development
   ```

3. Delete the release branch:
   ```bash
   git branch -d release/1.0.0
   git push origin --delete release/1.0.0
   ```

---

## 9. Example Commit Log

```plaintext
feat: add login form ui
fix: login form validation
style: apply prettier
refactor: optimize login form data processing
feat: add basic functionality for the signup form
test: add tests for signup form validation
fix: resolve error on empty signup form submission
docs: add instructions for using the signup form
chore: version 1.0.0
```
