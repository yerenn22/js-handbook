# Pull Requests Workflow

## Creating a Pull Request

1. Push your branch to the remote repository:
   ```bash
   git push origin feature/your-branch-name
   ```

2. Open a pull request in GitHub:
   - Base branch: `development`
   - Compare branch: `feature/your-branch-name`

3. Write a clear description:
   ```plaintext
   feat: add login functionality

   Added a login form with data validation and a basic UI.
   Fixed validation errors and optimized data processing logic.
   ```

4. Request reviews from team members.

## Merging a Pull Request

- Use the **squash and merge** strategy for clean commit history.
