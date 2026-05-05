# Onboarding Guide

Welcome to DevLink. This guide helps you understand the organization, choose the right route, and make your first contribution.

---

## Step 1: Understand the Organization

Before writing any code or documentation, familiarize yourself with how DevLink operates:

1. Read the [Organization Overview](overview.md) to understand our mission and structure.
2. Review the [Community Guidelines](community.md) to understand roles and expectations.
3. Read the [Code of Conduct](../CODE_OF_CONDUCT.md).
4. Skim the [Workflow Guide](../systems/workflow.md) to understand the issue-to-merge path.

---

## Step 2: Choose the Right Route

| Goal | Start here |
|---|---|
| Report a defect | [Bug report](https://github.com/devlinkorg/.github/issues/new?template=bug_report.yml) |
| Propose a workflow or feature improvement | [Feature request](https://github.com/devlinkorg/.github/issues/new?template=feature_request.yml) |
| Improve documentation | [Documentation update](https://github.com/devlinkorg/.github/issues/new?template=documentation.yml) |
| Ask for help before opening an issue | [GitHub Discussions](https://github.com/devlinkorg/.github/discussions) |
| Report a security issue | [Security Policy](https://github.com/devlinkorg/.github/security/policy) |

If you are unsure, start with a discussion. Maintainers can help turn the conversation into a scoped issue.

---

## Step 3: Choose a Guild

DevLink organizes work into domain-specific guilds. Review the available guilds and identify one that aligns with your skills and interests:

| Guild | Directory | Focus |
|---|---|---|
| Web Engineering | [`/guilds/web`](../guilds/web) | Frontend, APIs, full-stack |
| AI / Machine Learning | [`/guilds/ai-ml`](../guilds/ai-ml) | Models, data, MLOps |
| DevOps / Infrastructure | [`/guilds/devops`](../guilds/devops) | CI/CD, cloud, observability |

Read the guild README for specific onboarding instructions, active projects, and resources.

---

## Step 4: Set Up Your Environment

### General Setup

1. **Fork the repository** to your GitHub account.
2. **Clone your fork** locally:

   ```bash
   git clone https://github.com/<your-username>/.github.git
   cd .github
   ```

3. **Add the upstream remote:**

   ```bash
   git remote add upstream https://github.com/devlinkorg/.github.git
   ```

4. **Sync before starting work:**

   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```

### Project-Specific Setup

Each project under `/projects` has its own README with environment setup instructions. Follow those instructions for the specific project you intend to contribute to.

---

## Step 5: Find Your First Issue

1. Browse issues labeled [`good first issue`](https://github.com/devlinkorg/.github/issues?q=label%3A%22good+first+issue%22).
2. Comment on the issue to express your interest.
3. Wait for assignment or maintainer confirmation before starting work.
4. Ask clarifying questions in the issue so the final decision stays attached to the work.

---

## Step 6: Make Your First Contribution

1. Create a feature branch from `main`:

   ```bash
   git checkout -b docs/your-change-name
   ```

2. Make your changes following the [Contribution Guidelines](../CONTRIBUTING.md).
3. Commit using [Conventional Commits](https://www.conventionalcommits.org/):

   ```bash
   git commit -m "docs(scope): describe the change"
   ```

4. Push your branch and open a pull request:

   ```bash
   git push origin docs/your-change-name
   ```

5. Fill out the [PR template](../.github/pull_request_template.md) completely.
6. Include test evidence, such as link checks or manual Markdown preview notes.
7. Respond to review feedback promptly.

---

## Step 7: Continue Growing

After your first contribution:

- Take on progressively complex issues.
- Participate in [Technical Reviews](events.md) and knowledge-sharing sessions.
- Contribute to documentation and code reviews.
- Consider stepping into guild membership or maintainer responsibilities over time.

---

## Resources

| Resource | Link |
|---|---|
| Contribution Guidelines | [CONTRIBUTING.md](../CONTRIBUTING.md) |
| Architecture Documentation | [/systems/architecture.md](../systems/architecture.md) |
| Workflow Guide | [/systems/workflow.md](../systems/workflow.md) |
| Pull Request Template | [/.github/pull_request_template.md](../.github/pull_request_template.md) |
| Issue Chooser | [github.com/devlinkorg/.github/issues/new/choose](https://github.com/devlinkorg/.github/issues/new/choose) |
| Discussions | [github.com/devlinkorg/.github/discussions](https://github.com/devlinkorg/.github/discussions) |
| Code of Conduct | [CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md) |

---

## Questions

If you need help at any point during onboarding, open a [GitHub Discussion](https://github.com/devlinkorg/.github/discussions).
