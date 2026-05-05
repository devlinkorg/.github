# Sentinel

**Infrastructure monitoring and alerting system.**

[![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)](.)
[![Guild](https://img.shields.io/badge/guild-devops-orange?style=flat-square)](../../guilds/devops)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](../../LICENSE)

---

## Overview

Sentinel is an infrastructure monitoring and alerting system built for observability across distributed services. It collects metrics, evaluates alerting rules, and delivers notifications through configurable channels.

### Key Features

- Metric collection from multiple infrastructure sources
- Configurable alerting rules with threshold and anomaly detection
- Multi-channel notification delivery (email, Slack, webhook)
- Dashboard API for visualization integrations
- Health check aggregation across services
- Alert history and incident timeline tracking

---

## Architecture

```
sentinel/
├── src/
│   ├── collector/         # Metric collection agents
│   │   ├── sources/       # Source-specific collectors (HTTP, gRPC, system)
│   │   └── pipeline/      # Data ingestion pipeline
│   ├── engine/            # Alert evaluation engine
│   │   ├── rules/         # Rule definitions and parsing
│   │   ├── evaluator/     # Threshold and anomaly evaluation
│   │   └── state/         # Alert state management
│   ├── notifier/          # Notification delivery
│   │   ├── channels/      # Channel implementations (email, Slack, webhook)
│   │   └── templates/     # Notification templates
│   ├── api/               # REST API for configuration and queries
│   │   ├── routes/        # Route definitions
│   │   └── middleware/     # Authentication, rate limiting
│   ├── storage/           # Time-series data storage layer
│   └── shared/            # Shared utilities, types, and configuration
├── docs/
│   ├── deployment.md      # Deployment and operations guide
│   └── architecture.md    # Architecture decisions
└── README.md
```

---

## Technology Stack

| Layer | Technology | Rationale |
|---|---|---|
| Language | Go 1.22 | Performance, concurrency model suited for data pipelines |
| API Framework | Chi | Lightweight, idiomatic Go HTTP router |
| Time-Series DB | TimescaleDB | PostgreSQL-based, optimized for time-series workloads |
| Message Queue | NATS | Lightweight pub/sub for internal event routing |
| Cache | Redis | Alert state caching, rate limiting |
| Configuration | YAML | Human-readable, version-controllable rule definitions |
| Containerization | Docker | Consistent deployment across environments |

---

## Getting Started

### Prerequisites

- Go >= 1.22
- PostgreSQL >= 16.0 (with TimescaleDB extension)
- Redis >= 7.0
- Docker (optional, for containerized deployment)

### Setup

```bash
# Clone the repository
git clone https://github.com/devlink-org/devlink.git
cd devlink/projects/sentinel

# Install dependencies
go mod download

# Configure environment
cp .env.example .env
# Edit .env with your database and service configuration

# Run database migrations
make db-migrate

# Start the service
make run
```

### Environment Variables

| Variable | Description | Default |
|---|---|---|
| `DATABASE_URL` | TimescaleDB connection string | — |
| `REDIS_URL` | Redis connection string | `redis://localhost:6379` |
| `PORT` | API server port | `8080` |
| `NATS_URL` | NATS server URL | `nats://localhost:4222` |
| `LOG_LEVEL` | Logging verbosity | `info` |
| `ALERT_EVAL_INTERVAL` | Alert evaluation interval | `30s` |

---

## Configuration

### Alert Rules

Alert rules are defined in YAML:

```yaml
rules:
  - name: high_cpu_usage
    metric: system.cpu.usage_percent
    condition: "> 90"
    duration: 5m
    severity: critical
    channels:
      - slack
      - email
    labels:
      team: infrastructure

  - name: api_latency_p99
    metric: http.request.duration_p99
    condition: "> 500ms"
    duration: 2m
    severity: warning
    channels:
      - slack
```

### Notification Channels

```yaml
channels:
  slack:
    type: slack
    webhook_url: ${SLACK_WEBHOOK_URL}
    default_channel: "#alerts"

  email:
    type: email
    smtp_host: ${SMTP_HOST}
    from: alerts@devlink.org
    recipients:
      - oncall@devlink.org

  webhook:
    type: webhook
    url: ${WEBHOOK_URL}
    method: POST
    headers:
      Authorization: "Bearer ${WEBHOOK_TOKEN}"
```

---

## API Reference

See [docs/deployment.md](docs/deployment.md) for operational documentation.

### Quick Reference

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/v1/health` | Service health check |
| `GET` | `/api/v1/metrics` | Query collected metrics |
| `GET` | `/api/v1/alerts` | List active alerts |
| `GET` | `/api/v1/alerts/history` | Alert history with timeline |
| `POST` | `/api/v1/rules` | Create an alerting rule |
| `PUT` | `/api/v1/rules/:id` | Update an alerting rule |
| `DELETE` | `/api/v1/rules/:id` | Delete an alerting rule |
| `POST` | `/api/v1/silence` | Silence alerts for a duration |

---

## Development

### Commands

| Command | Description |
|---|---|
| `make run` | Start the service locally |
| `make build` | Compile the binary |
| `make test` | Run the test suite |
| `make test-integration` | Run integration tests |
| `make lint` | Run golangci-lint |
| `make db-migrate` | Run database migrations |
| `make docker-build` | Build Docker image |
| `make docker-run` | Run in Docker container |

### Testing

```bash
# Unit tests
make test

# Integration tests (requires running database)
make test-integration

# Coverage report
make test-coverage
```

---

## Deployment

### Docker

```bash
# Build
docker build -t devlink/sentinel:latest .

# Run
docker run -d \
  --name sentinel \
  -p 8080:8080 \
  --env-file .env \
  devlink/sentinel:latest
```

### Kubernetes

Helm charts are available in `deploy/helm/`:

```bash
helm install sentinel ./deploy/helm/sentinel \
  --namespace monitoring \
  --values values.production.yaml
```

---

## Contributing

1. Review the [Contribution Guidelines](../../CONTRIBUTING.md).
2. Look for issues labeled `project:sentinel` and `good first issue`.
3. Follow the branching and commit conventions.
4. Submit a PR using the [PR template](../../.github/pull_request_template.md).

---

## Project Lead

*To be assigned.*

---

## License

This project is part of [DevLink](../../README.md) and is licensed under the [MIT License](../../LICENSE).
