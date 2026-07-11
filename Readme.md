<p align="center">
  <img src="Git Cheat Sheet.png" width="500" alt="Git Cheat Sheet">
</p>

# <h1 align="center">Git Cheat Sheet</h1>

This cheat sheet provides an overview of essential Git commands categorized into **Beginner**, **Intermediate/Advanced**, and **Expert** levels.
Additionally, it highlights the **Most Used Git Commands** for quick reference, common issues with solutions, workflow instructions, and necessary prerequisites.

---

## Prerequisites & Setup

Before starting, ensure you have the following installed and configured:

- **Git**: Download and install from [git-scm.com](https://git-scm.com/)
- **Visual Studio Code**: Download from [code.visualstudio.com](https://code.visualstudio.com/)
- **Configure Git** (once installed):
  ```
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

> ## Resources

- [Official Git Documentation](https://git-scm.com/docs)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Guides](https://guides.github.com/introduction/git-cheat-sheet/)
- [W3Schools Git Tutorial](https://www.w3schools.com/git/)

---

> ## Responsible Usage & Credits

## Built by **Md Rakibul Hassan**

This guide promotes the effective, responsible, and ethical use of **Git and GitHub.**

Misuse, including unauthorized data access, modification, or damage, is strictly prohibited. **The author** is not responsible for any consequences arising from the misuse of these instructions.

All content, credits, and intellectual property belong to their respective owners. This guide is intended for educational and personal use only, supporting best practices in version control.

## Use Git and GitHub ethically.

_Happy Git-ing!_ _Happy coding!_
