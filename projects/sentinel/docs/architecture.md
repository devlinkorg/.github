# Sentinel — Architecture

## ADR-001: Language Selection

### Status

Accepted

### Context

Sentinel requires a language that handles concurrent metric collection, real-time alert evaluation, and high-throughput data ingestion efficiently.

### Decision

Use Go 1.22 as the primary language.

### Consequences

- Native concurrency via goroutines and channels aligns with the data pipeline model.
- Single binary deployment simplifies operations.
- Strong standard library reduces external dependency count.
- Team must maintain Go expertise.

---

## ADR-002: Time-Series Storage

### Status

Accepted

### Context

Sentinel needs to store and query time-series metric data with high write throughput and efficient range queries.

### Decision

Use TimescaleDB (PostgreSQL extension) as the time-series storage layer.

### Consequences

- Full SQL query capability for metric analysis.
- Automatic data partitioning and retention policies.
- Leverages existing PostgreSQL operational knowledge.
- Compression reduces storage costs for historical data.

---

## ADR-003: Internal Messaging

### Status

Accepted

### Context

The collector, alert engine, and notifier components need asynchronous communication for event-driven processing.

### Decision

Use NATS as the internal message broker.

### Consequences

- Lightweight footprint suitable for embedded deployment.
- At-most-once delivery is acceptable for internal metric routing.
- Simple pub/sub model maps cleanly to the component architecture.
- JetStream can be enabled for persistence if needed in the future.

---

## System Design

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  Collector   │────▶│   Storage   │◀────│  API Server │
│  (sources)   │     │ (TimescaleDB)│     │   (Chi)     │
└──────┬───────┘     └──────┬───────┘     └─────────────┘
       │                    │
       ▼                    ▼
┌─────────────┐     ┌─────────────┐
│    NATS     │────▶│   Engine    │
│  (pub/sub)  │     │ (evaluator) │
└─────────────┘     └──────┬───────┘
                           │
                           ▼
                    ┌─────────────┐
                    │  Notifier   │
                    │ (channels)  │
                    └─────────────┘
```

### Data Flow

1. **Collector** gathers metrics from configured sources on a scheduled interval.
2. Metrics are written to **Storage** (TimescaleDB) and published to **NATS**.
3. **Engine** subscribes to metric events, evaluates alert rules, and manages alert state.
4. When an alert fires, **Notifier** delivers notifications through configured channels.
5. **API Server** provides query access to metrics, alerts, rules, and configuration.
