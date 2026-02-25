# GitResolveMasterMainIntellijProject

## Resolving master/main Branch Conflict Between IntelliJ and GitHub

GitHub creates `main` as the default branch, while IntelliJ creates `master` by default. This project documents the steps to resolve that naming conflict.

### Steps Taken

1. Created the project locally in IntelliJ (defaults to `master` branch).
2. Added Git support to the project from within IntelliJ.
3. Created a new repository on GitHub.
4. Linked the local repository to the GitHub remote from within IntelliJ.
5. Renamed the local `master` branch to `main` and updated the remote:

```bash
git branch -m master main
git push -u origin main
git push origin --delete master
```

### Explanation

- `git branch -m master main` — renames the local branch from `master` to `main`.
- `git push -u origin main` — pushes the `main` branch to GitHub and sets it as the upstream tracking branch.
- `git push origin --delete master` — deletes the old `master` branch from the remote, leaving `main` as the only branch.