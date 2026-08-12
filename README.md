# Git Cheat Sheet

<p align="center">
  <img src="Git_Cheat_Sheet.png" alt="Git Cheat Sheet"width="700">
</p>

<p align="center">

![Git](https://img.shields.io/badge/Git-Cheat%20Sheet-orange?logo=git)
![GitHub](https://img.shields.io/badge/GitHub-Reference-black?logo=github)
![Beginner Friendly](https://img.shields.io/badge/Beginner-Friendly-brightgreen)
![Open Source](https://img.shields.io/badge/Open%20Source-Yes-blue)
![Stars](https://img.shields.io/github/stars/RR0327/git-cheat-sheet?style=social)

</p>

A practical Git and GitHub reference for developers — from first commit to advanced troubleshooting.

Whether you're learning Git for the first time or trying to fix a broken branch, this repository brings commonly used commands, workflows, troubleshooting steps, and advanced Git techniques into one place.

## Why Use This Cheat Sheet?

- Beginner → Expert Git commands
- Real-world Git troubleshooting
- Branching and merging workflows
- Push, pull, rebase, reset, and recovery guides
- GitHub collaboration commands
- Conventional commit guidelines
- Downloadable Git cheat sheet
- Practical examples you can copy and use

## Who Is This For?

- Students learning Git and GitHub
- Beginner developers
- Internship participants
- Software engineering teams
- Developers who need a quick Git reference

## What's Included?

1. Beginner Git commands
2. Intermediate and advanced commands
3. Expert Git commands
4. Most-used command quick reference
5. Common Git errors and solutions
6. Clone, work, and sync workflow
7. Adding individual files
8. Upstream branch troubleshooting
9. Git pull troubleshooting
10. Branch creation and pushing
11. Conventional commits
12. Downloadable cheat-sheet resources

## Downloadable Resources

Want an offline reference?

### Git Cheat Sheet PDF
[**Download the Git Cheat Sheet PDF**](./git-cheat-sheet-education.pdf)

A printable reference containing useful Git commands for quick offline access.

### Visual Cheat Sheet Image
[**View the Git Cheat Sheet Image**](./Git%20Cheat%20Sheet.png)

Useful for keeping Git commands nearby while working.

### Conventional Commits Guide
[**Read the Conventional Commits Guide**](./conventional-commits-guide.md)

Learn how to write structured commit messages such as:

```bash
feat: add authentication
fix: resolve login validation issue
docs: update installation guide
refactor: simplify API handler
```

---

## Table of Contents

- [Quick Reference](#quick-reference)
- [Prerequisites & Setup](#prerequisites--setup)
- [Beginner Commands](#1-beginner)
- [Intermediate & Advanced Commands](#2-intermediateadvanced)
- [Expert Commands](#3-expert)
- [Most Used Commands](#4-most-used-git-commands-quick-reference)
- [Common Git Issues & Solutions](#5-common-git-issues--solutions)
- [Git Workflow](#6-workflow-for-cloning-working-and-syncing)
- [Adding a Single File](#7-adding-a-single-file-to-an-existing-clone)
- [No Upstream Branch Fix](#8-git-push-issue-no-upstream-branch)
- [Git Pull Errors](#9-git-pull-error)
- [Creating & Pushing Branches](#10-creating-and-pushing-a-new-git-branch)
- [Conventional Commits](conventional-commits-guide.md)
- [Download Resources](#-downloadable-resources)

## Quick Reference

| Task | Command |
|---|---|
| Check repository status | `git status` |
| Clone a repository | `git clone <repository-url>` |
| Stage all changes | `git add .` |
| Commit changes | `git commit -m "message"` |
| Pull latest changes | `git pull origin main` |
| Push changes | `git push origin main` |
| Create a branch | `git switch -c branch-name` |
| Switch branches | `git switch branch-name` |
| View commit history | `git log --oneline` |
| Temporarily save changes | `git stash` |

---

## Prerequisites & Setup

Before starting, ensure you have the following installed and configured:

- **Git**: Download and install from [git-scm.com](https://git-scm.com/)
- **Visual Studio Code**: Download from [code.visualstudio.com](https://code.visualstudio.com/)
- **Configure Git** (once installed):
 ```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Optional:

- Set up SSH keys or credential helper for smoother authentication with remote repositories.

---

## 1. Beginner

### Basic commands to get started with Git

| Command        | Description                                | Example                                             |
| -------------- | ------------------------------------------ | --------------------------------------------------- |
| `git init`     | Initialize a new Git repository            | `git init`                                          |
| `git clone`    | Clone an existing repository               | `git clone https://github.com/user/repo.git`        |
| `git status`   | Check the status of your working directory | `git status`                                        |
| `git add`      | Stage changes for commit                   | `git add filename` or `git add .` or `git add *.py` |
| `git commit`   | Commit staged changes                      | `git commit -m "Message"`                           |
| `git branch`   | List, create, or delete branches           | `git branch`                                        |
| `git checkout` | Switch branches or restore files           | `git checkout branch-name`                          |
| `git merge`    | Merge branches                             | `git merge branch-name`                             |
| `git pull`     | Fetch and merge changes from remote        | `git pull origin main`                              |
| `git push`     | Push changes to remote                     | `git push origin main`                              |

---

## 2. Intermediate/Advanced

### Commands for more control and collaboration

| Command           | Description                                           | Example                                  |
| ----------------- | ----------------------------------------------------- | ---------------------------------------- |
| `git remote`      | Manage remote repositories                            | `git remote add origin url`              |
| `git fetch`       | Download objects and refs from another repository     | `git fetch`                              |
| `git rebase`      | Reapply commits on top of another base tip            | `git rebase branch-name`                 |
| `git stash`       | Temporarily store changes                             | `git stash`                              |
| `git cherry-pick` | Apply specific commits                                | `git cherry-pick commit_hash`            |
| `git reset`       | Reset current HEAD                                    | `git reset --hard commit_hash`           |
| `git revert`      | Create a new commit that undoes changes               | `git revert commit_hash`                 |
| `git log`         | Show commit logs                                      | `git log` or `git log --oneline --graph` |
| `git diff`        | Show changes between commits, working directory, etc. | `git diff`                               |
| `git tag`         | Create, list, or delete tags                          | `git tag v1.0`                           |

---

## 3. Expert

### Advanced and rarely used commands

| Command             | Description                                       | Example                                              |
| ------------------- | ------------------------------------------------- | ---------------------------------------------------- |
| `git filter-branch` | Rewrite history                                   | `git filter-branch --tree-filter 'rm -rf tmp/' HEAD` |
| `git cherry`        | Find commits not merged upstream                  | `git cherry -v`                                      |
| `git rerere`        | Reuse recorded resolution of conflicts            | `git rerere`                                         |
| `git blame`         | Show who last modified each line                  | `git blame filename`                                 |
| `git submodule`     | Manage submodules                                 | `git submodule update --init`                        |
| `git gc`            | Cleanup unnecessary files and optimize repository | `git gc`                                             |
| `git fsck`          | Verify the connectivity and validity of objects   | `git fsck`                                           |

---

## 4. Most Used Git Commands (Quick Reference)

| Command        | Description                     |
| -------------- | ------------------------------- |
| `git clone`    | Clone a repository              |
| `git status`   | Check current status            |
| `git add`      | Stage changes                   |
| `git commit`   | Commit staged changes           |
| `git push`     | Push to remote repository       |
| `git pull`     | Pull latest changes from remote |
| `git branch`   | List or create branches         |
| `git checkout` | Switch branches                 |
| `git merge`    | Merge branches                  |

---

## 5. Common Git Issues & Solutions

Below are typical issues faced when working with Git, along with their solutions:

### 1. Issue: **Merged code has conflicts that need resolution**

- **Symptom:** Git reports conflicts during merge or rebase.
- **Solution:** Open conflicting files, look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), and manually resolve the conflicts. After resolving:
  ```
  git add <file>
  git commit
  ```

---

### 2. Issue: **Accidentally committed to the wrong branch**

- **Symptom:** Committed changes on an unintended branch.
- **Solution:**
  - Switch to the correct branch:
    ```
    git checkout correct-branch
    ```
  - Cherry-pick commit(s) (if needed):
    ```
    git cherry-pick <commit-hash>
    ```
  - Optionally, reset the wrong branch:
    ```
    git checkout wrong-branch
    git reset --hard HEAD~1
    ```

---

### 3. Issue: **Local commits not pushing to remote (due to conflicts or diverged history)**

- **Symptom:** Push fails due to non-fast-forward updates.
- **Solution:**
  - Pull latest changes with rebase:
    ```
    git pull --rebase
    ```
  - Resolve any conflicts, then push:
    ```
    git push
    ```

---

### 4. Issue: **Lost files after reset or revert**

- **Symptom:** Files missing after a reset.
- **Solution:**
  - Check reflog to find lost commits/files:
    ```
    git reflog
    ```
  - Recover the commit:
    ```
    git checkout -b recovery_branch <commit_hash>
    ```

---

### 5. Issue: **Untracked files not added or committed**

- **Symptom:** Files left untracked.
- **Solution:**
  - Check untracked files:
    ```
    git status
    ```
  - Add files:
    ```
    git add <file>
    ```
  - Commit:
    ```
    git commit -m "Add new files"
    ```

---

### 6. Issue: **Large repository size slowing down operations**

- **Symptom:** Git repository becomes slow or bloated.
- **Solution:**
  - Clean up unnecessary files:
    ```
    git gc --prune=now --aggressive
    ```
  - Remove large unwanted files historically using `filter-branch` or tools like `bfg-repo-cleaner`.

---

### 7. Issue: **Conflicting changes between branches**

- **Symptom:** Conflicts arise when merging branches.
- **Solution:**
  - Resolve conflicts manually by editing files or using `git mergetool`.
  - Carefully rebase or merge branches, considering the history and changes to minimize conflicts.

---

## 6. Workflow for Cloning, Working, and Syncing

### Initial Setup

Open Command Prompt and run the following commands:

```
git clone https://github.com/username/repositoryname
ls
cd .\repositoryname\
git remote -v
code .
```

- This clones the repository, opens the folder in Visual Studio Code, and prepares it for work.

### Making Changes

After editing your files, commit and push your updates:

```
git add .
git commit -m "updated work"
git push origin main
```

### For Others (Collaborators)

If you haven't made local changes yet, you don’t need to git add or git commit before git pull.

If you’ve already cloned the repository and want to sync the latest changes, follow these commands:

```
git pull origin main
git add .
git commit -m "your message"
git push origin main
```

- This stages your changes, commits, and pulls the latest updates from the remote repository to keep your local copy current.

It's also a good idea to occasionally fetch and review the log:

```
git fetch
git log --oneline --graph --all
```

to understand the commit history.

---

## 7. Adding a Single File to an Existing Clone

If you've already cloned the repo and want to add a file:

# Check current status

git status

# Stage your new file

git add filename.ext

# Commit with message

git commit -m "Add: description of the new file"

# Pull latest changes (rebase)

git pull origin main --rebase

# Push your changes

git push origin main

Replace filename.ext with your actual filename and description.

---

## 8. Git Push Issue: No Upstream Branch

## Problem

When running:

```bash
git push
```

**Git displays**:

```bash
fatal: The current branch main has no upstream branch.
```

This happens because the local `main` branch is not linked to a remote branch on GitHub.

## Solution

### Check if a remote exists

```bash
git remote -v
```

> If you get something like:

```bash
origin https://github.com/USERNAME/Git_and_Github.git (fetch)
origin https://github.com/USERNAME/Git_and_Github.git (push)
```

**then your remote already exists.**

If nothing appears, then you haven't added a remote yet.

### If the remote exists

Set the upstream branch and push:

```bash
git push -u origin main
```

or

```bash
git push --set-upstream origin main
```

> This command does two things:

- pushes your code
- connects your local main branch to GitHub

### If no remote exists

Add the GitHub repository:

```bash
git remote add origin https://github.com/<username>/<repository>.git
```

Then push:

```bash
git push -u origin main
```

After the upstream branch is configured, future pushes only require:

```bash
git push
```

> If `git push -u origin main` **fails**

Run these commands and send me the output:

```bash
git remote -v
git branch -vv
git remote show origin
```

---

## 9. Git Pull Error

## Problem

Running the following command:

```bash
git pull
```

produced the error:

```bash
fatal: couldn't find remote ref refs/heads/django_template
```

Although the repository's default branch was `main`, Git was still trying to pull from a deleted or non-existent remote branch named `django_template`.

---

## Cause

The local branch was configured to track the remote branch:

```bash
origin/django_template
```

However, that branch had already been removed from the remote repository. Because the local Git configuration still referenced it, every `git pull` attempted to fetch a branch that no longer existed.

---

## Solution

### 1. Remove stale remote references

```bash
git remote prune origin
```

This removes references to remote branches that have been deleted.

---

### 2. Fetch the latest branches

```bash
git fetch origin main
```

This updates the local repository with the latest information from the `main` branch.

---

### 3. Pull from the correct branch

```bash
git pull origin main
```

This successfully downloads and merges the latest changes from the remote `main` branch.

---

## Result

The repository was updated successfully using a fast-forward merge, and all latest changes from the remote `main` branch were downloaded.

---

## Recommendation

If `git pull` continues to look for the deleted branch, update the upstream branch:

```bash
git branch --unset-upstream
git branch --set-upstream-to=origin/main <local-branch-name>
```

Replace `<local-branch-name>` with your current local branch name (for example, `main` or `master`).

You can check your current branch with:

```bash
git branch
```

## 10. Creating and Pushing a New Git Branch

## Problem

You want to create a new branch from the `main` branch, work on a new feature independently, and push the branch to GitHub without affecting the `main` branch.

---

## Solution

### 1. Verify you are on the `main` branch

```bash
git branch
```

Expected output:

```text
* main
```

If you are not on `main`, switch to it:

```bash
git switch main
```

---

### 2. Create and switch to a new branch

Replace `api` with your preferred branch name.

```bash
git switch -c api
```

Verify the current branch:

```bash
git branch
```

Expected output:

```bash
* api
  main
```

---

### 3. Make your changes

Modify, add, or delete files as needed.

Check the current status:

```bash
git status
```

---

### 4. Stage and commit your changes

```bash
git add .
git commit -m "feat(api): add REST API implementation"
```

---

### 5. Push the branch to GitHub

Since the branch does not yet exist on the remote repository:

```bash
git push -u origin api
```

The `-u` option sets the upstream branch, allowing future pushes with:

```bash
git push
```

---

### 6. Verify the branch on the remote

```bash
git branch -a
```

Expected output:

```bash
* api
  main
  remotes/origin/api
  remotes/origin/main
```

---

## Switching Between Branches

Switch to the `main` branch:

```bash
git switch main
```

Switch back to the `api` branch:

```bash
git switch api
```

---

## Workflow Diagram

```bash
main
  │
  │
  ├───────────────●───────────────●
                  \
                   \
api                 ●──────────────●
```

- `main` remains stable.
- `api` is used for feature development.
- Changes can later be merged into `main` using a pull request or `git merge`.

---

## Result

A new feature branch is created, development is isolated from the `main` branch, and the branch is successfully pushed to GitHub with upstream tracking configured. This workflow is the standard practice for collaborative Git development.

---

## 11. Git Push Failed with `remote: fatal error in commit_refs`

## Problem

While pushing commits to GitHub, the following error appears:

```bash
remote: fatal error in commit_refs
To https://github.com/your-username/your-repository.git
 ! [remote rejected] main -> main (failure)
error: failed to push some refs
```

This error means your local Git commands completed successfully, but the remote repository rejected the push. The issue is typically related to the remote repository or requires further investigation to determine the exact cause.

---

# Solution

Follow the steps below to diagnose and resolve the issue.

## Step 1: Check the Repository Status

Verify the current status of your local repository.

```bash
git status
```

Then inspect the most recent commits.

```bash
git log --oneline --graph --decorate -5
```

These commands help confirm that your working tree is clean and that the expected commits exist locally.

---

## Step 2: Verify the Remote Repository

Check that your repository is connected to the correct remote.

```bash
git remote -v
```

Ensure that both the fetch and push URLs point to the intended GitHub repository.

---

## Step 3: Synchronize with the Remote Repository

Fetch the latest changes from GitHub.

```bash
git fetch origin
```

Compare your local branch with the remote branch.

View commits that exist locally but have not been pushed:

```bash
git log --oneline origin/main..HEAD
```

View commits that exist on the remote but not locally:

```bash
git log --oneline HEAD..origin/main
```

This helps determine whether your local and remote branches have diverged.

---

## Step 4: Try Pushing Again

Sometimes the error is caused by a temporary issue on GitHub.

Retry the push:

```bash
git push
```

If the push succeeds, no further action is required.

If the error persists, continue to the next step.

---

## Step 5: Enable Verbose Output

Collect more detailed information about the push operation.

```bash
git push --verbose
```

- The command `git push --verbose` (or its shorthand `git push -v`) forces Git to run the upload process verbosely, outputting extra details about the connection and transmission.
- According to the official Git documentation, its main effect is showing the status of up-to-date references, which Git normally hides to keep terminal logs clean.

> Key Features of Verbose Mode

- Lists all branches: It prints confirmation lines for every branch evaluated, even those already up to date on the remote server.
- Server details: It displays the specific remote repository URL and communication steps used during data transfer.
- Troubleshooting aid: It helps diagnose frozen or stuck transfers by displaying explicit progress milestones.

Or enable Git tracing.

### Linux/macOS

```bash
GIT_TRACE=1 git push
```

### Windows PowerShell

```powershell
$env:GIT_TRACE=1
git push
```

The additional output can help identify the exact reason for the failure.

---

# Possible Causes

## 1. Temporary GitHub Server Issue (Most Common)

GitHub may occasionally experience temporary internal errors that reject pushes.

In this case:

- Wait a few minutes.
- Retry the push.
- Check GitHub's service status if the problem continues.

---

## 2. Branch Protection Rules

If the target branch is protected, GitHub usually returns an error similar to:

```text
protected branch hook declined
```

If you do not see this message, branch protection is unlikely to be the cause.

---

## 3. File or Repository Restrictions

Large files, Git LFS configuration, or certain repository policies may prevent a successful push.

Although renaming files generally does not cause this issue, repository rules or storage limitations could contribute to the failure.

---

# Commands to Collect Diagnostic Information

Run the following commands and review their outputs.

```bash
git status
```

```bash
git log --oneline --graph --decorate -5
```

```bash
git remote -v
```

```bash
git fetch origin
```

```bash
git push --verbose
```

These commands provide enough information to determine whether the issue originates from the local repository, the remote repository, or GitHub itself.

---

# Important Notes

Do **not** use the following commands unless you fully understand their effects.

```bash
git push --force
```

```bash
git reset --hard
```

Both commands can overwrite history or permanently discard local changes.

---

# Summary

If you encounter the `remote: fatal error in commit_refs` error:

1. Check the repository status.
2. Verify the remote configuration.
3. Fetch and compare the local and remote branches.
4. Retry the push.
5. Collect verbose output if the problem persists.
6. Review possible causes such as temporary GitHub issues, branch protection, or repository restrictions.

Following these steps will help you identify the root cause before applying any potentially destructive Git commands.

---

> ## Resources

- [Official Git Documentation](https://git-scm.com/docs)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Guides](https://guides.github.com/introduction/git-cheat-sheet/)
- [W3Schools Git Tutorial](https://www.w3schools.com/git/)

---

## Contributing

Contributions are welcome.

If you know a useful Git command, workflow, troubleshooting technique, or improvement:

1. Fork the repository
2. Create a new branch
3. Make your improvement
4. Commit your changes
5. Open a Pull Request

Please keep examples clear, practical, and beginner-friendly.

---

> ## Responsible Usage & Credits

## Built by **Md Rakibul Hassan**

This guide promotes the effective, responsible, and ethical use of **Git and GitHub.**

Misuse, including unauthorized data access, modification, or damage, is strictly prohibited. **The author** is not responsible for any consequences arising from the misuse of these instructions.

All content, credits, and intellectual property belong to their respective owners. This guide is intended for educational and personal use only, supporting best practices in version control.

## Use Git and GitHub ethically.

_Happy Git-ing!_ _Happy coding!_

---

## Support the Project

If this Git Cheat Sheet helped you solve a Git problem or learn something new, consider starring the repository.

A star also makes it easier to find the cheat sheet again later.
