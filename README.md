# DevOps Starter: My First CI Pipeline

Every time you push code or open a pull request, GitHub automatically
installs dependencies and runs the tests. Green check = safe to merge.
Red X = something broke, fix before merging.

## Setup
1. Create a new GitHub repo, then upload these files (keep the .github folder).
2. Commit to `main` and open the **Actions** tab. You should see "CI" running.

## Try it
1. Create a branch: `git checkout -b break-it`
2. In `app.py`, change `a + b` to `a - b`, then push and open a pull request.
3. Watch the pipeline fail (red X). Revert the change and watch it pass.
4. Add a new function plus a test for it.
