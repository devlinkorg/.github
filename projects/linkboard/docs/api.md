# LinkBoard — API Specification

## Base URL

```
https://api.devlink.org/linkboard/v1
```

## Authentication

All authenticated endpoints require a Bearer token in the `Authorization` header:

```
Authorization: Bearer <token>
```

Tokens are obtained via the `/auth/login` endpoint.

---

## Endpoints

### Authentication

#### `POST /auth/register`

Register a new user account.

**Request Body:**

```json
{
  "email": "user@example.com",
  "password": "securepassword",
  "displayName": "Jane Doe"
}
```

**Response:** `201 Created`

```json
{
  "id": "usr_a1b2c3d4",
  "email": "user@example.com",
  "displayName": "Jane Doe",
  "createdAt": "2026-01-15T10:30:00Z"
}
```

#### `POST /auth/login`

Authenticate and receive an access token.

**Request Body:**

```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

**Response:** `200 OK`

```json
{
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "expiresAt": "2026-01-16T10:30:00Z"
}
```

---

### Boards

#### `GET /boards`

List all boards accessible to the authenticated user.

**Response:** `200 OK`

```json
{
  "data": [
    {
      "id": "brd_x1y2z3",
      "name": "Sprint 12",
      "description": "Current sprint tasks",
      "memberCount": 5,
      "taskCount": 23,
      "createdAt": "2026-01-10T08:00:00Z"
    }
  ],
  "pagination": {
    "page": 1,
    "pageSize": 20,
    "total": 1
  }
}
```

#### `POST /boards`

Create a new board.

**Request Body:**

```json
{
  "name": "Sprint 13",
  "description": "Next sprint planning"
}
```

**Response:** `201 Created`

---

### Tasks

#### `GET /boards/:boardId/tasks`

List tasks for a specific board.

**Query Parameters:**

| Parameter | Type | Description |
|---|---|---|
| `status` | string | Filter by status (`todo`, `in_progress`, `done`) |
| `assignee` | string | Filter by assignee user ID |
| `page` | integer | Page number (default: 1) |
| `pageSize` | integer | Items per page (default: 20, max: 100) |

#### `POST /boards/:boardId/tasks`

Create a new task on a board.

**Request Body:**

```json
{
  "title": "Implement authentication flow",
  "description": "Add OAuth2 login support",
  "status": "todo",
  "priority": "high",
  "assigneeId": "usr_a1b2c3d4"
}
```

#### `PATCH /tasks/:taskId`

Update a task.

#### `DELETE /tasks/:taskId`

Delete a task.

---

## Error Responses

All errors follow a consistent format:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Email is required",
    "details": [
      {
        "field": "email",
        "message": "This field is required"
      }
    ]
  }
}
```

### Error Codes

| Code | HTTP Status | Description |
|---|---|---|
| `VALIDATION_ERROR` | 400 | Request body failed validation |
| `UNAUTHORIZED` | 401 | Missing or invalid authentication |
| `FORBIDDEN` | 403 | Insufficient permissions |
| `NOT_FOUND` | 404 | Resource not found |
| `CONFLICT` | 409 | Resource already exists |
| `INTERNAL_ERROR` | 500 | Unexpected server error |

---

## Rate Limiting

API requests are rate-limited per authenticated user:

| Tier | Limit |
|---|---|
| Standard | 100 requests/minute |
| Elevated | 500 requests/minute |

Rate limit headers are included in all responses:

```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 87
X-RateLimit-Reset: 1706104260
```
