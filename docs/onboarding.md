# Onboarding Guide

Welcome to DevLink. This guide will help you understand the organization, set up your environment, and start contributing.

---

## Step 1: Understand the Organization

Before writing any code, familiarize yourself with how DevLink operates:

1. Read the [Organization Overview](overview.md) to understand our mission and structure.
2. Review the [Community Guidelines](community.md) to understand roles and expectations.
3. Read the [Code of Conduct](../CODE_OF_CONDUCT.md).

---

## Step 2: Choose a Guild

DevLink organizes work into domain-specific guilds. Review the available guilds and identify one that aligns with your skills and interests:

| Guild | Directory | Focus |
|---|---|---|
| Web Engineering | [`/guilds/web`](../guilds/web) | Frontend, APIs, full-stack |
| AI / Machine Learning | [`/guilds/ai-ml`](../guilds/ai-ml) | Models, data, MLOps |
| DevOps / Infrastructure | [`/guilds/devops`](../guilds/devops) | CI/CD, cloud, observability |

Read the guild's README for specific onboarding instructions, active projects, and resources.

---

## Step 3: Set Up Your Environment

### General Setup

1. **Fork the repository** to your GitHub account.
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/<your-username>/devlink.git
   cd devlink
   ```
3. **Add the upstream remote:**
   ```bash
   git remote add upstream https://github.com/devlink-org/devlink.git
   ```

### Project-Specific Setup

Each project under `/projects` has its own README with environment setup instructions. Follow those instructions for the specific project you intend to contribute to.

---

## Step 4: Find Your First Issue

1. Browse issues labeled [`good first issue`](https://github.com/devlink-org/devlink/issues?q=label%3A%22good+first+issue%22).
2. Comment on the issue to express your interest.
3. Wait for assignment confirmation from a maintainer before starting work.

---

## Step 5: Make Your First Contribution

1. Create a feature branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
2. Make your changes following the [Contribution Guidelines](../CONTRIBUTING.md).
3. Commit using [Conventional Commits](https://www.conventionalcommits.org/):
   ```bash
   git commit -m "feat(scope): description of change"
   ```
4. Push your branch and open a Pull Request:
   ```bash
   git push origin feat/your-feature-name
   ```
5. Fill out the [PR template](../.github/pull_request_template.md) completely.
6. Respond to review feedback promptly.

---

## Step 6: Continue Growing

After your first contribution:

- Take on progressively complex issues.
- Participate in [Technical Reviews](events.md) and knowledge-sharing sessions.
- Contribute to documentation and code reviews.
- Consider stepping into a guild membership or maintainer role over time.

---

## Resources

| Resource | Link |
|---|---|
| Contribution Guidelines | [CONTRIBUTING.md](../CONTRIBUTING.md) |
| Architecture Documentation | [/systems/architecture.md](../systems/architecture.md) |
| Workflow Guide | [/systems/workflow.md](../systems/workflow.md) |
| Code of Conduct | [CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md) |

---

## Questions

If you need help at any point during onboarding, open a [Discussion](https://github.com/devlink-org/devlink/discussions) with the `onboarding` label, or reach out to your guild lead.
