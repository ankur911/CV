# Branch Policy & Workflow

This repository uses branch protection rules and a clear workflow for safe collaboration and deployment.  
Below is a summary of the current branch structure, protection settings, and contribution process.

---

## Branch Structure

- **main**  
  - Production/deployment branch (e.g., GitHub Pages source)
  - Only stable, reviewed code is merged here
- **develop**  
  - Integration branch for staging tested code before deployment
  - Always kept in sync with `main`
- **feature**  
  - Feature and development branch
  - All active work and contributions happen here

---

## Branch Protection Rules

### main

- **Require a pull request before merging**
- **Require at least 1 approval**
- **Require review from Code Owners**
  - `@ankur911` is listed as the code owner for all files (see `.github/CODEOWNERS`)
- **Require linear history**
  - All merges must be fast-forward; merge commits are not allowed

### develop

- **Same protection rules as `main` are recommended:**
  - Require a pull request before merging
  - Require at least 1 approval
  - Require review from Code Owners (`@ankur911`)
  - Require linear history

> Note: If "Restrict who can push" is not available in the GitHub UI for your account type, rely on the code owner and pull request approval rules for control.

---

## CODEOWNERS

A `.github/CODEOWNERS` file is used to require approval from @ankur911 for all changes:
```
* @ankur911
```

---

## Workflow Steps

1. **Feature development:**  
   - Work happens in the `feature` branch, or contributors can fork and open PRs targeting `develop`.

2. **Merge to develop:**  
   - When ready, changes are merged to `develop` via a pull request.
   - Any conflicts are resolved here.
   - PR must be approved by @ankur911.

3. **Sync develop and main:**  
   - After verification, merge `develop` into `main` via pull request.
   - This ensures no conflicts or unstable code reaches production.

4. **Deployment:**  
   - `main` is always ready and stable for deployment (e.g., GitHub Pages).

---

## Contribution Guide

- Open pull requests from `feature` (or forks) into `develop`.
- All PRs require approval from @ankur911 (code owner).
- No direct pushes to `main` or `develop`.
- Only fast-forward merges are allowed (no merge commits).

---

## Additional Notes

- Empty directories cannot be created on GitHub; always add a file inside.
- If you do not see certain protection options (e.g., "Restrict who can push"), your repository/account type may not support them.
- Only @ankur911 can approve and merge changes to protected branches.

---

_Last updated: 2025-08-21_
