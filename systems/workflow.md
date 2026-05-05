# Workflow Guide

## Overview

This document defines the standard GitHub workflow for project lifecycle management, contributor routing, review, release, and incident response within DevLink.

The canonical repository target for public workflow links is `https://github.com/devlinkorg/.github`.

---

## GitHub Entry Points

| Need | Route |
|---|---|
| Report a bug | [Bug issue form](https://github.com/devlinkorg/.github/issues/new?template=bug_report.yml) |
| Request a feature or workflow improvement | [Feature issue form](https://github.com/devlinkorg/.github/issues/new?template=feature_request.yml) |
| Request a documentation update | [Documentation issue form](https://github.com/devlinkorg/.github/issues/new?template=documentation.yml) |
| Ask a question or discuss an idea | [GitHub Discussions](https://github.com/devlinkorg/.github/discussions) |
| Report a vulnerability | [Security Policy](https://github.com/devlinkorg/.github/security/policy) |
| Open a pull request | [Pull Request Template](../.github/pull_request_template.md) |

---

## Development Workflow

### Issue-to-Merge Flow

All scoped work begins with an issue unless a maintainer confirms that a small change can proceed directly.

```text
Issue created -> Triage -> Assigned -> Branch -> Pull request -> Review -> Merge -> Issue closed
```

| Stage | Owner | Action |
|---|---|---|
| Issue created | Author | Opens the correct issue form with enough context to route the work. |
| Triage | Maintainer or guild lead | Applies labels, checks scope, asks follow-up questions, and decides priority. |
| Assigned | Maintainer | Assigns an owner or confirms the contributor can start. |
| Branch | Contributor | Creates a branch from `main` using the documented naming convention. |
| Pull request | Contributor | Opens a PR, links the issue, fills out the PR template, and adds test evidence. |
| Review | Reviewer | Checks correctness, routing impact, documentation impact, and test evidence. |
| Merge | Maintainer | Squash-merges approved work into `main`. |
| Closure | Maintainer or author | Confirms the linked issue is closed or updated with the final outcome. |

### Development Cycle

```text
main
  |
  |-- docs/update-routing-guide
  |     |
  |     `-- Pull request -> Review -> Squash merge
  |
main
```

1. **Branch** from `main` using the naming convention in [CONTRIBUTING.md](../CONTRIBUTING.md).
2. **Develop** the change with focused commits.
3. **Verify** the change with relevant checks, including documentation checks for docs-only changes.
4. **Open** a pull request and complete the PR template.
5. **Review** feedback and iterate until approved.
6. **Merge** via squash merge into `main`.
7. **Clean up** by deleting the feature branch and confirming issue status.

### Documentation-Only Changes

Documentation-only changes are first-class contributions in this repository.

- Use the documentation issue form when the work starts from a docs gap.
- Preview Markdown when changing tables, diagrams, badges, or navigation sections.
- Run link checks or manually verify changed links.
- Keep public GitHub links pointed at `https://github.com/devlinkorg/.github`.
- Update `CHANGELOG.md` when the change affects public contributor workflow, routing, or governance expectations.

### Code Review

Code review is required for all changes. Reviews focus on:

- **Correctness:** Does the change do what it claims?
- **Clarity:** Is the workflow or implementation easy to follow?
- **Completeness:** Are edge cases, docs, and tests covered?
- **Consistency:** Does it follow repository conventions and route contributors correctly?

---

## Release Workflow

### Versioning

DevLink projects follow [Semantic Versioning](https://semver.org/):

```text
MAJOR.MINOR.PATCH

MAJOR - Breaking changes
MINOR - New features that are backward compatible
PATCH - Bug fixes that are backward compatible
```

### Release Process

1. **Prepare:** Ensure `main` is stable and all required checks pass.
2. **Changelog:** Update `CHANGELOG.md` with changes since the last release.
3. **Tag:** Create a version tag, such as `git tag -a v1.2.0 -m "Release v1.2.0"`.
4. **Publish:** Push the tag to trigger release automation when configured.
5. **Announce:** Notify relevant channels or discussions.

---

## Project Lifecycle

### Proposal

New projects are proposed through [GitHub Discussions](https://github.com/devlinkorg/.github/discussions). Proposals should include:

- Problem statement
- Proposed solution
- Technical approach
- Resource requirements
- Guild ownership

### Initiation

Approved projects are initialized using the standard project structure:

```text
project-name/
|-- README.md
|-- src/
`-- docs/
```

### Active Development

Projects in active development follow the development workflow described above. Progress is tracked through GitHub issues, pull requests, and project boards when configured.

### Maintenance

Projects that have reached stability enter maintenance mode:

- Critical bug fixes only.
- Dependency updates on a scheduled cadence.
- Documentation kept current.

### Archival

Projects that are no longer actively maintained are archived:

- Repository is marked as archived on GitHub.
- README is updated with an archival notice.
- Documentation remains accessible.

---

## Incident Response

### Severity Levels

| Level | Description | Response Time |
|---|---|---|
| P0 - Critical | Production system down, data loss | Immediate |
| P1 - High | Major feature broken, significant impact | Within 4 hours |
| P2 - Medium | Non-critical issue, workaround available | Within 24 hours |
| P3 - Low | Minor issue, minimal impact | Within 1 week |

### Process

1. **Detect:** Issue identified through monitoring, user report, or maintainer review.
2. **Triage:** Assign severity and notify the responsible team.
3. **Mitigate:** Apply an immediate fix or workaround.
4. **Resolve:** Implement the permanent fix through the standard PR workflow.
5. **Postmortem:** Document root cause, impact, and preventive measures.

Security vulnerabilities must follow the [Security Policy](../SECURITY.md) and should not be reported through public issues.

---

## References

- [Architecture Standards](architecture.md)
- [Contribution Guidelines](contribution-guidelines.md)
- [CONTRIBUTING.md](../CONTRIBUTING.md)
- [GitHub Discussions](https://github.com/devlinkorg/.github/discussions)
