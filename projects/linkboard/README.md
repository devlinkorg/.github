# LinkBoard

**Real-time collaborative task management platform.**

[![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)](.)
[![Guild](https://img.shields.io/badge/guild-web_engineering-blue?style=flat-square)](../../guilds/web)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](../../LICENSE)

---

## Overview

LinkBoard is a real-time collaborative task management platform designed for engineering teams. It provides structured workflows for tracking tasks, managing sprints, and coordinating work across distributed teams.

### Key Features

- Real-time collaboration with live updates
- Kanban and list-based task views
- Sprint planning and tracking
- Team workspaces with role-based access control
- Activity feeds and notification system
- REST API for integrations

---

## Architecture

```
linkboard/
├── src/
│   ├── api/              # REST API layer
│   │   ├── routes/       # Route definitions
│   │   ├── middleware/    # Authentication, validation, error handling
│   │   └── controllers/  # Request handlers
│   ├── core/             # Business logic
│   │   ├── tasks/        # Task management domain
│   │   ├── boards/       # Board management domain
│   │   └── users/        # User management domain
│   ├── data/             # Data access layer
│   │   ├── models/       # Database models
│   │   ├── migrations/   # Schema migrations
│   │   └── repositories/ # Data access abstractions
│   ├── realtime/         # WebSocket and event handling
│   └── shared/           # Shared utilities and types
├── docs/
│   ├── api.md            # API specification
│   └── architecture.md   # Architecture decisions
└── README.md
```

---

## Technology Stack

| Layer | Technology | Rationale |
|---|---|---|
| Runtime | Node.js 20 LTS | Event-driven architecture suited for real-time features |
| Framework | Express.js | Lightweight, well-supported HTTP framework |
| Database | PostgreSQL 16 | Relational data model, strong consistency guarantees |
| Cache | Redis | Session management, real-time pub/sub |
| Real-time | Socket.IO | WebSocket abstraction with fallback support |
| ORM | Prisma | Type-safe database queries, migration management |
| Language | TypeScript | Static typing for maintainability |

---

## Getting Started

### Prerequisites

- Node.js >= 20.0.0
- PostgreSQL >= 16.0
- Redis >= 7.0

### Setup

```bash
# Clone the repository
git clone https://github.com/devlink-org/devlink.git
cd devlink/projects/linkboard

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Edit .env with your database and Redis connection strings

# Run database migrations
npm run db:migrate

# Start development server
npm run dev
```

### Environment Variables

| Variable | Description | Default |
|---|---|---|
| `DATABASE_URL` | PostgreSQL connection string | — |
| `REDIS_URL` | Redis connection string | `redis://localhost:6379` |
| `PORT` | Server port | `3000` |
| `JWT_SECRET` | JWT signing secret | — |
| `NODE_ENV` | Runtime environment | `development` |

---

## API Reference

See [docs/api.md](docs/api.md) for the complete API specification.

### Quick Reference

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Register a new user |
| `POST` | `/api/auth/login` | Authenticate and receive token |
| `GET` | `/api/boards` | List boards for current user |
| `POST` | `/api/boards` | Create a new board |
| `GET` | `/api/boards/:id/tasks` | List tasks for a board |
| `POST` | `/api/boards/:id/tasks` | Create a task on a board |
| `PATCH` | `/api/tasks/:id` | Update a task |
| `DELETE` | `/api/tasks/:id` | Delete a task |

---

## Development

### Commands

| Command | Description |
|---|---|
| `npm run dev` | Start development server with hot reload |
| `npm run build` | Compile TypeScript for production |
| `npm run start` | Start production server |
| `npm run test` | Run test suite |
| `npm run test:watch` | Run tests in watch mode |
| `npm run lint` | Run ESLint |
| `npm run db:migrate` | Run database migrations |
| `npm run db:seed` | Seed database with sample data |

### Testing

Tests are organized by domain:

```
src/
├── core/tasks/__tests__/
├── core/boards/__tests__/
├── api/routes/__tests__/
└── shared/__tests__/
```

Run the full suite:

```bash
npm run test
```

---

## Contributing

1. Review the [Contribution Guidelines](../../CONTRIBUTING.md).
2. Look for issues labeled `project:linkboard` and `good first issue`.
3. Follow the branching and commit conventions.
4. Submit a PR using the [PR template](../../.github/pull_request_template.md).

---

## Project Lead

*To be assigned.*

---

## License

This project is part of [DevLink](../../README.md) and is licensed under the [MIT License](../../LICENSE).
