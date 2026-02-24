## Code Quality and Development Tooling Changes

This project now includes a standardized development workflow focused on code consistency, formatting, and commit validation.

The main additions are:

- `ESLint` configured using modern flat configuration.
- `Prettier` integration for automatic formatting.
- `Husky` git hooks for enforcing quality checks.
- `Commitlint` validation for Conventional Commits.
- `VSCode` workspace recommendations.

---

## What ESLint is Doing

The project uses `ESLint` to enforce code quality rules and detect potential problems in `TypeScript` and `React` code.

The configured rules primarily focus on:

- Maintaining consistent import ordering.
- Detecting unsafe or problematic coding patterns.
- Enforcing Web Core Vitals performance recommendations.
- Supporting TypeScript-aware linting.

### Import Ordering

Imports are automatically organized according to these groups:

1. Built-in Node modules
2. External dependencies
3. Internal project modules
4. Sibling modules
5. Parent directory modules
6. Index files

Additionally:

- Imports inside the same group are sorted alphabetically (case-insensitive).
- Blank lines are enforced between different import groups.

---

## What Prettier is Doing

Prettier is responsible for automatic code formatting.

It ensures:

- Consistent indentation.
- Consistent spacing.
- Standardized quote usage.
- Clean and readable code structure.

Prettier formatting is automatically applied when saving files (if the editor is configured accordingly).

Prettier works alongside ESLint, and conflicts between formatting rules are disabled to avoid overlapping behavior.

---

## Git Hooks Enforcement

### Pre-commit Hook

Before allowing a commit, the repository automatically runs:

- ESLint auto-fix on staged files.
- Prettier formatting on staged files.

If unresolved linting or formatting errors remain, the commit will be blocked.

---

### Commit Message Validation

Commit messages must follow the Conventional Commits standard.

Allowed commit types include:

- `feat` – New feature implementation.
- `fix` – Bug fixes.
- `chore` – Maintenance and tooling updates.
- `docs` – Documentation changes.
- `refactor` – Code restructuring without behavior change.
- `test` – Test-related changes.
- `build` – Build system modifications.
- `ci` – Continuous integration changes.
- `perf` – Performance improvements.
- `revert` – Reverting previous commits.

Example of a valid commit message:

`feat: add movie gallery search feature`

Invalid commit messages will be rejected automatically.

---

## Editor Integration

The workspace configuration includes recommendations for:

- ESLint extension for code analysis and auto-fixing.
- Prettier extension for formatting.

Recommended settings:

- Format on save enabled.
- ESLint code actions enabled.

---

## Development Environment Requirements

- `Node.js` version 22 or higher is recommended.
- Using a Node Version Manager (such as `nvm`) is strongly suggested when working across multiple projects.

---

## Summary

This setup ensures:

- Consistent code formatting.
- Automatic linting and error detection.
- Structured commit history.
- Reduced repository noise.
- Improved team collaboration and maintainability.
