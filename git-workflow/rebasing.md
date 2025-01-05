# Rebasing Workflow

## Rebasing Your Branch

1. Sync your branch with `development`:
   ```bash
   git checkout development
   git pull origin development
   git checkout feature/your-branch-name
   git rebase development
   ```

2. Resolve conflicts (if any):
   - Edit conflicting files.
   - Mark as resolved:
     ```bash
     git add .
     git rebase --continue
     ```

3. Push the updated branch:
   ```bash
   git push origin feature/your-branch-name --force
   ```
