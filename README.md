<div align="center">

# DevLink

**An execution-driven engineering infrastructure focused on building real-world systems through structured collaboration and production-grade workflows.**

<br />

[![License: MIT](https://img.shields.io/badge/License-MIT-3FB950.svg?style=flat-square&labelColor=161B22)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-58A6FF.svg?style=flat-square&labelColor=161B22)](CONTRIBUTING.md)
[![Conduct](https://img.shields.io/badge/Code_of_Conduct-enforced-D2A8FF.svg?style=flat-square&labelColor=161B22)](CODE_OF_CONDUCT.md)
[![Security](https://img.shields.io/badge/Security-policy-F85149.svg?style=flat-square&labelColor=161B22)](SECURITY.md)

---

[Overview](#overview) · [Architecture](#architecture) · [Domains](#engineering-domains) · [Projects](#active-projects) · [Getting Started](#getting-started) · [Contributing](#contributing)

</div>

---

## Overview

DevLink is a structured engineering organization that designs, builds, and deploys production-grade software systems. Our focus is on measurable output, technical rigor, and scalable collaboration across distributed teams.

This repository serves as the **central hub** for all organizational activity — project catalogs, domain structures, contribution workflows, architectural standards, and community resources.

### Core Principles

| Principle | Description |
|---|---|
| **Execution over ideation** | Every initiative is tied to a deployable outcome. |
| **Production-grade standards** | All code follows industry-standard quality gates. |
| **Structured collaboration** | Clear workflows, ownership, and accountability at every level. |
| **Domain specialization** | Teams are organized by technical domain for depth and expertise. |
| **Open contribution** | Transparent processes that welcome external contributors. |

---

## Architecture

DevLink operates as a modular engineering system with clearly defined boundaries between domains, projects, and shared infrastructure.

```
DevLink
├── domains (guilds)        — Specialized engineering verticals
│   ├── Web Engineering
│   ├── AI / Machine Learning
│   └── DevOps / Infrastructure
├── projects                — Active product and system builds
├── systems                 — Shared architecture, workflows, and standards
└── community               — Onboarding, events, and documentation
```

For detailed architectural documentation, see [`/systems/architecture.md`](systems/architecture.md).

---

## Engineering Domains

DevLink organizes engineering work into **guilds** — domain-specific groups that own a vertical of technical expertise.

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

```
project-name/
├── README.md           — Overview, setup, and usage
├── src/                — Source code
└── docs/               — Architecture decisions, API docs
```

Browse all projects in the [`/projects`](projects/) directory.

---

## Repository Structure

```
.
├── .github/                        # GitHub configuration
│   ├── ISSUE_TEMPLATE/             # Standardized issue templates
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   ├── documentation.md
│   │   └── config.yml
│   ├── workflows/                  # CI/CD automation
│   │   ├── ci.yml
│   │   ├── docs.yml
│   │   └── stale.yml
│   └── pull_request_template.md
├── docs/                           # Organization documentation
│   ├── overview.md
│   ├── community.md
│   ├── events.md
│   └── onboarding.md
├── guilds/                         # Domain-based engineering groups
│   ├── web/
│   ├── ai-ml/
│   └── devops/
├── projects/                       # Active project catalog
│   ├── linkboard/
│   │   ├── README.md
│   │   ├── src/
│   │   └── docs/
│   └── sentinel/
│       ├── README.md
│       ├── src/
│       └── docs/
├── systems/                        # Architecture and standards
│   ├── architecture.md
│   ├── workflow.md
│   └── contribution-guidelines.md
├── profile/                        # GitHub organization profile
│   └── README.md
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
└── README.md
```

---

## Getting Started

### For New Contributors

1. Read the [Onboarding Guide](docs/onboarding.md) to understand the organizational structure.
2. Review the [Contribution Guidelines](CONTRIBUTING.md) for workflow and standards.
3. Explore the [Guilds](guilds/) to find a domain that matches your expertise.
4. Browse [open issues](https://github.com/devlink-org/devlink/issues) labeled `good first issue`.

### For Project Leads

1. Review the [Architecture Documentation](systems/architecture.md) for system design standards.
2. Follow the [Workflow Guide](systems/workflow.md) for project lifecycle management.
3. Use the [Project Template](projects/) structure when initializing new projects.

---

## Contributing

We welcome contributions from engineers at all levels. Our contribution process is designed to be clear, predictable, and respectful of everyone's time.

**Quick start:**

1. Fork the repository
2. Create a feature branch (`feat/your-feature-name`)
3. Commit using [Conventional Commits](https://www.conventionalcommits.org/)
4. Open a Pull Request against `main`

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
| Changelog | [CHANGELOG.md](CHANGELOG.md) |

---

## License

This project is licensed under the [MIT License](LICENSE).

---

<div align="center">

**DevLink** — Building systems that ship.

</div>
