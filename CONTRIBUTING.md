# Contributing to DevLink

Thank you for your interest in contributing to DevLink. This guide explains the GitHub workflow, documentation expectations, and review standards for this repository.

---

## Table of Contents

- [Where to Go Next](#where-to-go-next)
- [Prerequisites](#prerequisites)
- [Issue Workflow](#issue-workflow)
- [Branching Strategy](#branching-strategy)
- [Commit Conventions](#commit-conventions)
- [Pull Request Workflow](#pull-request-workflow)
- [Documentation-Only Changes](#documentation-only-changes)
- [Quality Standards](#quality-standards)
- [Review Process](#review-process)

---

## Where to Go Next

| Need | Route |
|---|---|
| New contributor setup | [docs/onboarding.md](docs/onboarding.md) |
| Full workflow details | [systems/workflow.md](systems/workflow.md) |
| Bug report | [Bug issue form](https://github.com/devlinkorg/.github/issues/new?template=bug_report.yml) |
| Feature or workflow request | [Feature issue form](https://github.com/devlinkorg/.github/issues/new?template=feature_request.yml) |
| Documentation improvement | [Documentation issue form](https://github.com/devlinkorg/.github/issues/new?template=documentation.yml) |
| Questions or ideas | [GitHub Discussions](https://github.com/devlinkorg/.github/discussions) |
| Security report | [Security Policy](https://github.com/devlinkorg/.github/security/policy) |

---

## Prerequisites

Before contributing, ensure you have:

1. Read and agreed to the [Code of Conduct](CODE_OF_CONDUCT.md).
2. Reviewed the [Onboarding Guide](docs/onboarding.md).
3. Checked whether the work belongs to a specific [Guild](guilds/) or project.
4. Searched existing [issues](https://github.com/devlinkorg/.github/issues) and [discussions](https://github.com/devlinkorg/.github/discussions).

---

## Issue Workflow

All scoped work should start from an issue unless a maintainer confirms that the change is small enough to proceed directly.

1. Choose the correct issue form from the [issue chooser](https://github.com/devlinkorg/.github/issues/new/choose).
2. Include enough context for maintainers to route and prioritize the work.
3. Wait for triage when the change affects workflow, governance, security, or project direction.
4. Link your pull request to the issue with `Closes #123`, `Fixes #123`, or a clear explanation if no issue exists.

Use [GitHub Discussions](https://github.com/devlinkorg/.github/discussions) for early ideas, broad questions, or proposals that are not ready for implementation.

---

## Branching Strategy

DevLink follows a **trunk-based development** model with short-lived feature branches.

### Branch Naming Convention

| Prefix | Purpose | Example |
|---|---|---|
| `feat/` | New feature | `feat/contributor-dashboard` |
| `fix/` | Bug fix | `fix/broken-onboarding-link` |
| `docs/` | Documentation update | `docs/update-routing-guide` |
| `refactor/` | Code or documentation structure refactor | `refactor/workflow-sections` |
| `test/` | Test additions or updates | `test/docs-link-check` |
| `chore/` | Maintenance tasks | `chore/update-actions` |

### Branch Rules

- Create branches from `main`.
- Keep branches focused and short-lived.
- Keep branches up to date with `main` before merge.
- Do not commit directly to `main`.

---

## Commit Conventions

All commits must follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Format

```text
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

| Type | Description |
|---|---|
| `feat` | New feature or workflow capability |
| `fix` | Bug fix |
| `docs` | Documentation changes |
| `style` | Formatting changes with no content or behavior change |
| `refactor` | Structure change that does not alter intended behavior |
| `test` | Test additions or updates |
| `chore` | Build, tooling, or maintenance changes |
| `ci` | CI/CD configuration changes |

### Examples

```text
docs(onboarding): update first contribution route

fix(templates): route security reports to policy page

ci(docs): exclude discussion URLs from link checker
```

### Rules

- Use the imperative mood in the description, such as "add" rather than "added".
- Do not end the description with a period.
- Keep the first line under 72 characters.
- Reference related issues in the footer when applicable.

---

## Pull Request Workflow

### Before Opening a PR

- Confirm your branch is based on `main`.
- Run the relevant checks listed in [Test Evidence](.github/pull_request_template.md).
- Verify changed links route to `https://github.com/devlinkorg/.github` unless intentionally external.
- Update documentation when workflow, routing, templates, or expectations change.

### PR Requirements

- Use the [Pull Request Template](.github/pull_request_template.md).
- Provide a clear summary of what changed and why.
- Link the issue or explain why no issue is needed.
- Include test evidence, even for documentation-only changes.
- Identify changelog impact.

### Review and Merge

- All PRs require at least one approving review before merge.
- Reviewers should respond within 48 hours when possible.
- Authors should address all blocking feedback before requesting re-review.
- PRs are squash-merged into `main`.
- The author or maintainer closes the loop by ensuring the linked issue is closed or updated.

---

## Documentation-Only Changes

This repository is primarily documentation, routing, and workflow scaffolding, so documentation-only changes still need careful review.

For documentation-only PRs:

- Check local links and important public GitHub links.
- Preview rendered Markdown when structure, tables, diagrams, or badges change.
- Keep terminology consistent across `README.md`, `CONTRIBUTING.md`, `docs/`, `systems/`, and `profile/`.
- Update the issue forms or PR template when contributor routing changes.
- Add a changelog entry when the change affects public workflow expectations.

---

## Quality Standards

### Documentation

- Write for the next contributor who has not seen the internal conversation.
- Prefer direct links to the canonical route over duplicate instructions.
- Use ASCII diagrams and punctuation unless a file already requires otherwise.
- Keep README files current for all projects and significant modules.

### Code and Project Scaffolds

- Write clear, self-documenting code.
- Follow the principle of least surprise.
- Keep functions and modules focused.
- Document public APIs and complex operational decisions.

### Testing

- New code features must include corresponding tests.
- Bug fixes must include regression coverage when possible.
- Documentation changes should include link checks, lint checks, or manual rendered review.

---

## Review Process

### For Reviewers

- Check that the contributor route is clear from issue to PR to merge.
- Focus on correctness, maintainability, and adherence to standards.
- Be constructive and specific in feedback.
- Approve only when blocking concerns are resolved.

### For Authors

- Respond to all review comments.
- Do not dismiss reviews without discussion.
- Keep PRs small and focused for faster review cycles.
- Update the PR description when the implementation changes during review.

---

## Questions

If you have questions about the contribution process, open a [GitHub Discussion](https://github.com/devlinkorg/.github/discussions).

Thank you for contributing to DevLink. Every contribution strengthens the systems we build together.
