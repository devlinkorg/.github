# Sentinel — Deployment and Operations Guide

## Deployment Options

### Docker (Recommended)

```bash
# Build the image
docker build -t devlink/sentinel:latest .

# Run with environment file
docker run -d \
  --name sentinel \
  -p 8080:8080 \
  --env-file .env \
  --restart unless-stopped \
  devlink/sentinel:latest
```

### Kubernetes

```bash
# Deploy using Helm
helm install sentinel ./deploy/helm/sentinel \
  --namespace monitoring \
  --create-namespace \
  --values values.production.yaml
```

### Binary

```bash
# Build the binary
make build

# Run directly
./bin/sentinel --config config.yaml
```

---

## Configuration Reference

### Core Settings

| Setting | Environment Variable | Default | Description |
|---|---|---|---|
| Port | `PORT` | `8080` | HTTP API server port |
| Log Level | `LOG_LEVEL` | `info` | Logging verbosity (debug, info, warn, error) |
| Database URL | `DATABASE_URL` | — | TimescaleDB connection string |
| Redis URL | `REDIS_URL` | `redis://localhost:6379` | Redis connection string |
| NATS URL | `NATS_URL` | `nats://localhost:4222` | NATS server URL |

### Collector Settings

| Setting | Environment Variable | Default | Description |
|---|---|---|---|
| Collection Interval | `COLLECT_INTERVAL` | `15s` | Metric collection frequency |
| Batch Size | `COLLECT_BATCH_SIZE` | `100` | Metrics per batch write |
| HTTP Timeout | `COLLECT_HTTP_TIMEOUT` | `5s` | Timeout for HTTP-based collectors |

### Alert Engine Settings

| Setting | Environment Variable | Default | Description |
|---|---|---|---|
| Evaluation Interval | `ALERT_EVAL_INTERVAL` | `30s` | Alert rule evaluation frequency |
| Notification Cooldown | `ALERT_COOLDOWN` | `5m` | Minimum time between repeat notifications |
| Max Active Alerts | `ALERT_MAX_ACTIVE` | `1000` | Maximum concurrent active alerts |

---

## Health Checks

### Liveness

```
GET /health/live
```

Returns `200 OK` if the process is running.

### Readiness

```
GET /health/ready
```

Returns `200 OK` if all dependencies (database, Redis, NATS) are connected and responsive.

**Response:**

```json
{
  "status": "ready",
  "checks": {
    "database": "ok",
    "redis": "ok",
    "nats": "ok"
  }
}
```

---

## Monitoring

### Prometheus Metrics

Sentinel exposes Prometheus-compatible metrics at `/metrics`:

| Metric | Type | Description |
|---|---|---|
| `sentinel_metrics_collected_total` | Counter | Total metrics collected |
| `sentinel_alerts_evaluated_total` | Counter | Total alert evaluations |
| `sentinel_alerts_fired_total` | Counter | Total alerts fired |
| `sentinel_notifications_sent_total` | Counter | Total notifications sent |
| `sentinel_collection_duration_seconds` | Histogram | Collection cycle duration |
| `sentinel_evaluation_duration_seconds` | Histogram | Evaluation cycle duration |

### Grafana Dashboards

Pre-built Grafana dashboards are available in `deploy/grafana/`:

- `sentinel-overview.json` — System overview and key metrics
- `sentinel-alerts.json` — Alert activity and history
- `sentinel-collector.json` — Collection pipeline performance

---

## Operational Runbook

### Scenario: High Alert Evaluation Latency

1. Check `sentinel_evaluation_duration_seconds` for trends.
2. Review the number of active alert rules — consider consolidation.
3. Verify database query performance for metric lookups.
4. Scale evaluation workers if resource-bound.

### Scenario: Notification Delivery Failures

1. Check `sentinel_notifications_sent_total` for drops.
2. Verify notification channel credentials (Slack webhook, SMTP).
3. Review rate limits on external notification services.
4. Check network connectivity from the Sentinel instance.

### Scenario: Database Connection Issues

1. Verify the `DATABASE_URL` is correct and accessible.
2. Check TimescaleDB connection pool utilization.
3. Review PostgreSQL logs for connection limit errors.
4. Restart the service if connections are in a stale state.

---

## Backup and Recovery

### Data Retention

Configure metric data retention via environment variable:

```
METRIC_RETENTION_DAYS=90
```

Metrics older than the retention period are automatically purged.

### Database Backup

```bash
# Full backup
pg_dump $DATABASE_URL > sentinel_backup_$(date +%Y%m%d).sql

# Restore
psql $DATABASE_URL < sentinel_backup_20260105.sql
```
