# Workflow Guide

## Overview

This document defines the standard workflows for project lifecycle management, development, and release processes within DevLink.

---

## Development Workflow

### 1. Issue Triage

All work begins with a GitHub issue.

```
Issue Created → Labeled → Triaged → Assigned → In Progress → In Review → Done
```

| Stage | Owner | Action |
|---|---|---|
| Created | Author | Opens issue using a template |
| Labeled | Maintainer | Applies priority, type, and guild labels |
| Triaged | Guild Lead | Validates scope and assigns priority |
| Assigned | Maintainer | Assigns to a contributor |
| In Progress | Contributor | Development work begins |
| In Review | Reviewer | Pull request is reviewed |
| Done | Maintainer | PR merged, issue closed |

### 2. Development Cycle

```
main ─────────────────────────────────────────────── main
       \                                         /
        feat/feature-name ──── PR ──── Review ──┘
```

1. **Branch** from `main` using the naming convention (`feat/`, `fix/`, etc.).
2. **Develop** the solution, committing frequently with conventional commits.
3. **Test** locally — run linters, unit tests, and integration tests.
4. **Push** the branch and open a Pull Request.
5. **Review** — address feedback, iterate until approved.
6. **Merge** via squash merge into `main`.
7. **Clean up** — delete the feature branch.

### 3. Code Review

Code review is a required step for all changes. Reviews focus on:

- **Correctness** — Does the code do what it claims?
- **Clarity** — Is the code readable and maintainable?
- **Completeness** — Are edge cases handled? Are tests included?
- **Consistency** — Does it follow project conventions?

---

## Release Workflow

### Versioning

DevLink projects follow [Semantic Versioning](https://semver.org/):

```
MAJOR.MINOR.PATCH

MAJOR — Breaking changes
MINOR — New features (backward compatible)
PATCH — Bug fixes (backward compatible)
```

### Release Process

1. **Prepare** — Ensure `main` is stable and all CI checks pass.
2. **Tag** — Create a version tag: `git tag -a v1.2.0 -m "Release v1.2.0"`.
3. **Changelog** — Update CHANGELOG.md with all changes since the last release.
4. **Publish** — Push the tag to trigger the release workflow.
5. **Announce** — Notify relevant channels of the release.

---

## Project Lifecycle

### Proposal

New projects are proposed via a GitHub Discussion with the `project-proposal` label. Proposals must include:

- Problem statement
- Proposed solution
- Technical approach
- Resource requirements
- Guild ownership

### Initiation

Approved projects are initialized using the standard project template:

```
project-name/
├── README.md
├── src/
└── docs/
```

### Active Development

Projects in active development follow the development workflow described above. Progress is tracked through GitHub Projects.

### Maintenance

Projects that have reached stability enter maintenance mode:

- Critical bug fixes only.
- Dependency updates on a scheduled cadence.
- Documentation kept current.

### Archival

Projects that are no longer actively maintained are archived:

- Repository is marked as archived on GitHub.
- README is updated with archival notice.
- Documentation remains accessible.

---

## Incident Response

### Severity Levels

| Level | Description | Response Time |
|---|---|---|
| P0 — Critical | Production system down, data loss | Immediate |
| P1 — High | Major feature broken, significant impact | Within 4 hours |
| P2 — Medium | Non-critical issue, workaround available | Within 24 hours |
| P3 — Low | Minor issue, minimal impact | Within 1 week |

### Process

1. **Detect** — Issue identified through monitoring or user report.
2. **Triage** — Assign severity and notify the responsible team.
3. **Mitigate** — Apply immediate fix or workaround.
4. **Resolve** — Implement permanent fix via standard PR workflow.
5. **Postmortem** — Document root cause, impact, and preventive measures.

---

## References

- [Architecture Standards](architecture.md)
- [Contribution Guidelines](contribution-guidelines.md)
- [CONTRIBUTING.md](../CONTRIBUTING.md)
