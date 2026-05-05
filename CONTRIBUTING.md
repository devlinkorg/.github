# Contributing to DevLink

Thank you for your interest in contributing to DevLink. This document outlines the standards, workflows, and expectations for all contributors.

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Branching Strategy](#branching-strategy)
- [Commit Conventions](#commit-conventions)
- [Pull Request Workflow](#pull-request-workflow)
- [Code Quality Standards](#code-quality-standards)
- [Issue Guidelines](#issue-guidelines)
- [Review Process](#review-process)

---

## Prerequisites

Before contributing, ensure you have:

1. Read and agreed to the [Code of Conduct](CODE_OF_CONDUCT.md).
2. Reviewed the [Onboarding Guide](docs/onboarding.md).
3. Familiarized yourself with the relevant [Guild](guilds/) standards for your domain.

---

## Branching Strategy

DevLink follows a **trunk-based development** model with short-lived feature branches.

### Branch Naming Convention

| Prefix | Purpose | Example |
|---|---|---|
| `feat/` | New feature | `feat/user-authentication` |
| `fix/` | Bug fix | `fix/login-redirect-loop` |
| `docs/` | Documentation update | `docs/update-onboarding` |
| `refactor/` | Code refactoring | `refactor/api-client-structure` |
| `test/` | Test additions or updates | `test/auth-unit-tests` |
| `chore/` | Maintenance tasks | `chore/update-dependencies` |

### Branch Rules

- All branches are created from `main`.
- Branches must be up-to-date with `main` before merging.
- Stale branches (no activity for 14 days) are subject to cleanup.
- Direct commits to `main` are not permitted.

---

## Commit Conventions

All commits must follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Format

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

| Type | Description |
|---|---|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation changes |
| `style` | Formatting changes (no logic change) |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test` | Adding or updating tests |
| `chore` | Build process or tooling changes |
| `perf` | Performance improvement |
| `ci` | CI/CD configuration changes |

### Examples

```
feat(auth): add OAuth2 login flow

fix(api): resolve null pointer in user endpoint

docs(readme): update project structure section
```

### Rules

- Use the imperative mood in the description ("add", not "added").
- Do not end the description with a period.
- Keep the first line under 72 characters.
- Reference related issues in the footer (e.g., `Closes #42`).

---

## Pull Request Workflow

### 1. Before Opening a PR

- Ensure your branch is up-to-date with `main`.
- Run all applicable linters and tests locally.
- Verify that your changes do not introduce regressions.

### 2. PR Requirements

- Use the [Pull Request Template](/.github/pull_request_template.md).
- Provide a clear, concise title following commit conventions.
- Include a description of **what** changed and **why**.
- Link related issues.
- Add relevant labels.

### 3. Review Process

- All PRs require at least **one approving review** before merge.
- Reviewers should respond within **48 hours**.
- Address all review comments before requesting re-review.
- Use "Request Changes" for blocking issues and "Comment" for suggestions.

### 4. Merging

- PRs are merged via **squash merge** to maintain a clean commit history.
- The PR author is responsible for resolving merge conflicts.
- Delete the feature branch after merge.

---

## Code Quality Standards

### General

- Write clear, self-documenting code.
- Follow the principle of least surprise.
- Prefer readability over cleverness.
- Keep functions and methods focused (single responsibility).

### Documentation

- All public APIs must be documented.
- Complex logic requires inline comments explaining the **why**, not the **what**.
- README files are required for all projects and significant modules.

### Testing

- New features must include corresponding tests.
- Bug fixes must include a regression test.
- Maintain or improve existing test coverage.

### Linting and Formatting

- All code must pass the project's configured linters.
- Use the project's established formatting configuration.
- Do not disable linting rules without justification and team approval.

---

## Issue Guidelines

### Creating Issues

- Search existing issues before creating a new one.
- Use the appropriate [Issue Template](/.github/ISSUE_TEMPLATE/).
- Provide sufficient context for reproduction (for bugs) or justification (for features).
- Apply relevant labels.

### Labels

| Label | Purpose |
|---|---|
| `good first issue` | Suitable for new contributors |
| `bug` | Confirmed defect |
| `enhancement` | Feature request |
| `documentation` | Documentation improvement |
| `help wanted` | Open for community contribution |
| `priority: high` | Requires immediate attention |
| `priority: low` | Can be addressed when capacity allows |

---

## Review Process

### For Reviewers

- Review within 48 hours of assignment.
- Focus on correctness, maintainability, and adherence to standards.
- Be constructive and specific in feedback.
- Approve only when all blocking concerns are resolved.

### For Authors

- Respond to all review comments.
- Do not dismiss reviews without discussion.
- Keep PRs small and focused for faster review cycles.

---

## Questions

If you have questions about the contribution process, open a [Discussion](https://github.com/devlink-org/devlink/discussions) or reach out to a guild lead.

---

Thank you for contributing to DevLink. Every contribution strengthens the systems we build together.
