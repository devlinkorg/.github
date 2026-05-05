# LinkBoard — Architecture

## ADR-001: Application Architecture

### Status

Accepted

### Context

LinkBoard requires a backend architecture that supports real-time collaboration, RESTful API access, and reliable data persistence. The system must handle concurrent users editing shared boards and tasks.

### Decision

Adopt a layered architecture with the following boundaries:

- **API Layer** — HTTP request handling, input validation, authentication
- **Core Layer** — Business logic, domain rules, use case orchestration
- **Data Layer** — Database access, caching, data transformation
- **Real-time Layer** — WebSocket connections, event broadcasting

### Consequences

- Clear separation of concerns enables independent testing of each layer.
- The real-time layer can scale independently of the REST API.
- Additional complexity in managing event consistency between layers.

---

## ADR-002: Database Selection

### Status

Accepted

### Context

LinkBoard needs a database that supports relational data modeling (users, boards, tasks with relationships), transactional consistency, and efficient querying.

### Decision

Use PostgreSQL 16 as the primary data store, with Redis for session management and real-time pub/sub.

### Consequences

- Strong ACID guarantees for task and board operations.
- Redis provides low-latency caching and pub/sub for real-time features.
- Operational complexity of managing two data stores.

---

## ADR-003: Real-Time Communication

### Status

Accepted

### Context

Users need to see task updates (creation, status changes, assignments) in real-time without page refreshes.

### Decision

Use Socket.IO for WebSocket-based real-time communication with automatic fallback to HTTP long-polling.

### Consequences

- Reliable real-time delivery across browser environments.
- Built-in room management maps cleanly to board-scoped updates.
- Additional server memory per connected client.
