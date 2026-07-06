# Conventional Commits Guide

A standardized format for writing commit messages that improves readability, collaboration, automation, and release management.

---

## Basic Format

```bash
<type>(<scope>): <short summary>

<optional body>

<optional footer>
```

### Examples

```bash
feat(auth): add login with Google OAuth
fix(api): resolve null pointer in user endpoint
docs(readme): update installation instructions
```

---

## Quick Rules

- Use lowercase for the commit type.
- Write the summary in the imperative mood (e.g., `add`, `fix`, `update`).
- Keep the summary concise (around 50–72 characters when possible).
- Do not end the summary with a period.
- Use the body to explain **why** the change was made, not **what** changed.
- Use the footer for issue references or breaking changes.

---

## Complete List of Commit Types

| Type       | Description                                                                                 |
| ---------- | ------------------------------------------------------------------------------------------- |
| `feat`     | Introduces a new feature.                                                                   |
| `fix`      | Fixes a bug.                                                                                |
| `docs`     | Documentation-only changes.                                                                 |
| `style`    | Formatting or code style changes that do not affect functionality.                          |
| `refactor` | Code changes that neither fix a bug nor add a feature.                                      |
| `perf`     | Improves performance.                                                                       |
| `test`     | Adds or updates tests.                                                                      |
| `build`    | Changes affecting the build system or dependencies.                                         |
| `ci`       | Changes to CI/CD configuration or scripts.                                                  |
| `chore`    | Maintenance tasks and miscellaneous changes that do not modify application source or tests. |
| `revert`   | Reverts a previous commit.                                                                  |

---

## Detailed Breakdown

### `feat` — New Feature

Introduces new functionality.

```bash
feat(payment): add Stripe payment integration
feat(search): implement full-text search
feat: add dark mode toggle
```

---

### `fix` — Bug Fix

Resolves a bug or unintended behavior.

```bash
fix(login): prevent crash on empty email field
fix(api): handle 404 errors gracefully
fix: correct date formatting on dashboard
```

---

### `docs` — Documentation

Documentation-only changes.

```bash
docs(api): update endpoint descriptions
docs(readme): add installation guide
docs: fix typo in contributing guide
```

---

### `style` — Code Style

Formatting changes that do not affect program behavior.

```bash
style: reformat code with Prettier
style: add missing semicolons
style(header): fix indentation
```

---

### `refactor` — Code Refactoring

Improves code structure without changing behavior.

```bash
refactor(auth): extract validation logic to helper
refactor: simplify conditional statements
refactor(utils): rename ambiguous variables
```

---

### `perf` — Performance Improvement

Improves application performance.

```bash
perf(db): add index on frequently queried fields
perf(images): implement lazy loading
perf: reduce bundle size by tree-shaking
```

---

### `test` — Testing

Adds or updates tests.

```bash
test(auth): add unit tests for login flow
test: increase test coverage for user module
test(api): fix broken integration tests
```

---

### `build` — Build System

Changes related to build tools or dependencies.

```bash
build: upgrade webpack to v5
build(deps): add lodash dependency
build: configure Babel for TypeScript
```

---

### `ci` — Continuous Integration

Changes to CI/CD workflows or automation.

```bash
ci: add GitHub Actions workflow
ci: update Node version in pipeline
ci(travis): fix deploy script
```

---

### `chore` — Maintenance

Routine maintenance tasks that do not modify application source code or tests.

```bash
chore: update .gitignore
chore: add .editorconfig
chore: configure ESLint rules
```

---

### `revert` — Revert

Reverts a previous commit.

```bash
revert: revert "feat: add user avatar upload"
revert: revert commit abc1234
```

---

## Scope

The optional scope identifies the area of the project affected by the change.

```bash
feat(auth): add password reset flow
fix(navbar): correct mobile menu behavior
docs(readme): add quick start section
```

### Common Scopes

- `auth`
- `api`
- `ui`
- `db`
- `config`
- `deps`
- `user`
- `payment`
- `search`
- `header`
- `footer`
- `modal`

---

## Commit Body

The body is optional but useful for explaining the reason behind a change.

Use it to describe:

- Why the change was necessary.
- Important implementation details.
- Any additional context reviewers should know.

Example:

```bash
feat(auth): add password reset email

Users can now request password reset links through email.
This reduces support requests and improves account recovery.
```

---

## Commit Footer

The footer is optional and is commonly used for issue references, metadata, or breaking changes.

Examples:

```bash
fix(api): validate request payload

Fixes #42
```

```bash
feat(user): add profile settings

Closes #118
Reviewed-by: Jane Doe
```

Common footer keywords:

- `Fixes #123`
- `Closes #123`
- `Resolves #123`

GitHub automatically closes linked issues when these commits are merged into the default branch.

---

## Breaking Changes

Use `!` after the type or scope to indicate a breaking change.

```bash
feat(api)!: change response format of user endpoint
refactor!: remove deprecated v1 routes
```

Alternatively, specify the breaking change in the footer.

```bash
feat: upgrade to React 18

BREAKING CHANGE: lifecycle methods have changed.
```

---

## Good vs. Bad Commit Messages

Good

```bash
feat(auth): add password reset endpoint
fix(api): handle missing authentication token
docs(readme): update installation instructions
```

Bad

```bash
Update code
Fix bug
Changes
Final update
misc
```

Good commit messages clearly describe the purpose of the change.

---

## Commit Structure

```bash
feat(cart): add quantity selector
```

```
feat      → Commit type
(cart)    → Optional scope
add...    → Short summary
```

---

## Quick Reference

| Task                               | Commit Type |
| ---------------------------------- | ----------- |
| Add a new feature                  | `feat`      |
| Fix a bug                          | `fix`       |
| Update documentation               | `docs`      |
| Format code                        | `style`     |
| Refactor code                      | `refactor`  |
| Improve performance                | `perf`      |
| Add or update tests                | `test`      |
| Update build tools or dependencies | `build`     |
| Modify CI/CD workflows             | `ci`        |
| Maintenance tasks                  | `chore`     |
| Revert a commit                    | `revert`    |

---

## References

- Conventional Commits Specification: https://www.conventionalcommits.org/
- Angular Commit Message Guidelines: https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit
