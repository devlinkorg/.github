<div align="center">

# DevLink

**An execution-driven engineering infrastructure focused on building real-world systems through structured collaboration and production-grade workflows.**

<br />

[![License: MIT](https://img.shields.io/badge/License-MIT-3FB950.svg?style=flat-square&labelColor=161B22)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-58A6FF.svg?style=flat-square&labelColor=161B22)](CONTRIBUTING.md)
[![Conduct](https://img.shields.io/badge/Code_of_Conduct-enforced-D2A8FF.svg?style=flat-square&labelColor=161B22)](CODE_OF_CONDUCT.md)
[![Security](https://img.shields.io/badge/Security-policy-F85149.svg?style=flat-square&labelColor=161B22)](SECURITY.md)

---

[Overview](#overview) | [GitHub Workflow](#github-workflow) | [Architecture](#architecture) | [Domains](#engineering-domains) | [Projects](#active-projects) | [Getting Started](#getting-started)

</div>

---

## Overview

DevLink is a structured engineering organization that designs, builds, and deploys production-grade software systems. Our focus is on measurable output, technical rigor, and scalable collaboration across distributed teams.

This repository serves as the **central hub** for organizational documentation, contributor routing, project catalogs, domain structures, workflow standards, and community resources.

### Core Principles

| Principle | Description |
|---|---|
| **Execution over ideation** | Every initiative is tied to a deployable outcome. |
| **Production-grade standards** | All code follows industry-standard quality gates. |
| **Structured collaboration** | Clear workflows, ownership, and accountability at every level. |
| **Domain specialization** | Teams are organized by technical domain for depth and expertise. |
| **Open contribution** | Transparent processes that welcome external contributors. |

---

## GitHub Workflow

Use these entry points when you need to take action:

| Need | Go here |
|---|---|
| Start contributing | [Onboarding Guide](docs/onboarding.md) |
| Report a bug | [Bug report](https://github.com/devlinkorg/.github/issues/new?template=bug_report.yml) |
| Request a feature or workflow improvement | [Feature request](https://github.com/devlinkorg/.github/issues/new?template=feature_request.yml) |
| Improve documentation | [Documentation update](https://github.com/devlinkorg/.github/issues/new?template=documentation.yml) |
| Ask a question | [GitHub Discussions](https://github.com/devlinkorg/.github/discussions) |
| Report a vulnerability | [Security Policy](https://github.com/devlinkorg/.github/security/policy) |
| Open a pull request | [Pull Request Template](.github/pull_request_template.md) |

For the full issue-to-merge process, see the [Workflow Guide](systems/workflow.md).

---

## Architecture

DevLink operates as a modular engineering system with clearly defined boundaries between domains, projects, and shared infrastructure.

```text
DevLink
|-- guilds/       Specialized engineering verticals
|   |-- web/      Web Engineering
|   |-- ai-ml/    AI / Machine Learning
|   `-- devops/   DevOps / Infrastructure
|-- projects/     Active product and system builds
|-- systems/      Shared architecture, workflows, and standards
`-- docs/         Onboarding, events, and community documentation
```

For detailed architectural documentation, see [`/systems/architecture.md`](systems/architecture.md).

---

## Engineering Domains

DevLink organizes engineering work into **guilds**, domain-specific groups that own a vertical of technical expertise.

| Guild | Focus Area | Key Technologies | Directory |
|---|---|---|---|
| **Web Engineering** | Frontend systems, APIs, full-stack platforms | React, Next.js, Node.js, PostgreSQL | [`/guilds/web`](guilds/web) |
| **AI / Machine Learning** | Model development, data pipelines, MLOps | PyTorch, scikit-learn, MLflow, FastAPI | [`/guilds/ai-ml`](guilds/ai-ml) |
| **DevOps / Infrastructure** | CI/CD, cloud architecture, observability | Terraform, Kubernetes, Prometheus | [`/guilds/devops`](guilds/devops) |

Each guild maintains its own project catalog, resource library, and contribution standards.

---

## Active Projects

Projects are maintained under the [`/projects`](projects/) directory. Each project follows a standardized structure with dedicated source code, documentation, and architecture decisions.

| Project | Domain | Status | Description |
|---|---|---|---|
| [**LinkBoard**](projects/linkboard/) | Web | Active | Real-time collaborative task management platform |
| [**Sentinel**](projects/sentinel/) | DevOps | Active | Infrastructure monitoring and alerting system |

### Project Structure

```text
project-name/
|-- README.md    Overview, setup, and usage
|-- src/         Source code
`-- docs/        Architecture decisions and API docs
```

Browse all projects in the [`/projects`](projects/) directory.

---

## Repository Structure

```text
.
|-- .github/       GitHub issue forms, PR template, and automation
|-- docs/          Organization documentation
|-- guilds/        Domain-based engineering groups
|-- projects/      Active project catalog
|-- systems/       Architecture, workflow, and contribution standards
|-- profile/       GitHub organization profile
|-- CHANGELOG.md
|-- CODE_OF_CONDUCT.md
|-- CONTRIBUTING.md
|-- LICENSE
|-- SECURITY.md
`-- README.md
```

---

## Getting Started

### For New Contributors

1. Read the [Onboarding Guide](docs/onboarding.md) to understand the organization and contribution path.
2. Review the [Contribution Guidelines](CONTRIBUTING.md) for branch, commit, PR, and review expectations.
3. Explore the [Guilds](guilds/) to find a domain that matches your expertise.
4. Browse [open issues](https://github.com/devlinkorg/.github/issues) labeled `good first issue`.
5. Ask questions in [GitHub Discussions](https://github.com/devlinkorg/.github/discussions) when you need help choosing a path.

### For Project Leads

1. Review the [Architecture Documentation](systems/architecture.md) for system design standards.
2. Follow the [Workflow Guide](systems/workflow.md) for project lifecycle management.
3. Use the [Project Template](projects/) structure when initializing new projects.

---

## Contributing

We welcome contributions from engineers at all levels. Our process is designed to be clear, predictable, and respectful of everyone's time.

**Quick start:**

1. Open or choose an issue from the [issue tracker](https://github.com/devlinkorg/.github/issues).
2. Create a branch from `main` using the documented naming conventions.
3. Commit using [Conventional Commits](https://www.conventionalcommits.org/).
4. Open a pull request against `main` and complete the [PR template](.github/pull_request_template.md).

For the complete guide, see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Standards and Governance

| Document | Description |
|---|---|
| [Architecture](systems/architecture.md) | System design principles and technology guidelines |
| [Workflow](systems/workflow.md) | Development, release, and incident response processes |
| [Contribution Guidelines](systems/contribution-guidelines.md) | Code quality, documentation, and testing standards |
| [Security Policy](SECURITY.md) | Vulnerability reporting and security practices |
| [Code of Conduct](CODE_OF_CONDUCT.md) | Community behavior standards |

---

## Community

| Resource | Link |
|---|---|
| Organization Overview | [docs/overview.md](docs/overview.md) |
| Community Guide | [docs/community.md](docs/community.md) |
| Events and Initiatives | [docs/events.md](docs/events.md) |
| GitHub Discussions | [github.com/devlinkorg/.github/discussions](https://github.com/devlinkorg/.github/discussions) |
| Changelog | [CHANGELOG.md](CHANGELOG.md) |

---

## License

This project is licensed under the [MIT License](LICENSE).

---

<div align="center">

**DevLink** - Building systems that ship.

</div>
