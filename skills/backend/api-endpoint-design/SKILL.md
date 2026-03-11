
---

name: api-endpoint-design
description: Design production-grade API endpoints for SaaS systems with strong architecture, security, consistency, and operational readiness.
category: backend
version: 1.0
------------

# API Endpoint Design

## Purpose

Design backend API endpoints following professional SaaS engineering standards suitable for production environments.

This skill ensures APIs are:

* consistent
* secure
* scalable
* maintainable
* observable
* backward compatible

The agent must avoid ad-hoc endpoint creation and instead follow a structured API design process.

---

# When to Use This Skill

Use this skill whenever:

* designing a new API endpoint
* exposing backend functionality through HTTP
* structuring a REST API
* defining service interfaces
* planning SaaS backend modules

Typical SaaS domains include:

* user management
* authentication
* organizations / tenants
* billing
* subscriptions
* projects
* internal services

---

# Core Architectural Principles

## 1. Resource-Oriented API Design

Endpoints must represent **resources**, not actions.

Correct:

GET /users
POST /users
GET /users/{id}
PATCH /users/{id}

Avoid:

POST /createUser
GET /getUsers
POST /updateUserData

Resources should represent real domain entities.

Examples:

* users
* organizations
* subscriptions
* invoices
* projects

---

## 2. Consistent HTTP Method Semantics

Use standard REST semantics:

| Method | Purpose              |
| ------ | -------------------- |
| GET    | Retrieve resource(s) |
| POST   | Create new resource  |
| PUT    | Replace resource     |
| PATCH  | Partial update       |
| DELETE | Remove resource      |

Rules:

* GET must be **idempotent**
* POST must create resources
* PATCH should update partial data
* DELETE must not expose internal errors

---

## 3. Clear Route Structure

Routes must be predictable and hierarchical.

Example:

/organizations/{orgId}/projects
/organizations/{orgId}/users
/projects/{projectId}/tasks

Avoid deep nesting beyond 3 levels.

---

# Input Validation Rules

All external input must be validated before reaching business logic.

Validation must include:

* request body
* query parameters
* path parameters
* headers when relevant

Common validation concerns:

* type validation
* required fields
* maximum size
* allowed values
* sanitization

Never trust client input.

---

# Layered Architecture

Endpoints must follow strict separation of concerns.

Architecture:

Route
↓
Controller
↓
Service
↓
Repository / Data Layer

Responsibilities:

Route
Defines endpoint path and method.

Controller
Handles request/response mapping.

Service
Contains business logic.

Repository
Handles persistence and database access.

Business logic must **never be placed in routes**.

---

# Response Structure Standardization

All responses must follow a predictable schema.

Success response:

```json
{
  "success": true,
  "data": {},
  "meta": {}
}
```

Error response:

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable message"
  }
}
```

Error messages must be safe for public exposure.

Never return:

* stack traces
* database errors
* internal class names

---

# Pagination Standards

All list endpoints must support pagination.

Example:

GET /users?page=1&limit=20

Response:

```json
{
  "success": true,
  "data": [],
  "meta": {
    "page": 1,
    "limit": 20,
    "total": 250
  }
}
```

Default limits should be enforced to avoid large queries.

---

# Idempotency Rules

Operations that may be retried must support idempotency.

Examples:

* payment creation
* subscription changes
* order processing

Techniques:

* idempotency keys
* request hashing
* transaction checks

---

# API Versioning

APIs must support versioning to prevent breaking clients.

Preferred strategies:

URL versioning:

/api/v1/users

Alternative:

Header-based versioning.

Rules:

* never silently break existing endpoints
* maintain backward compatibility when possible

---

# Security Requirements

Every endpoint must consider:

Authentication
Authorization
Input validation
Rate limiting
Audit logging

Security rules:

* endpoints must verify identity
* access control must check permissions
* sensitive endpoints require stricter validation

Never expose internal system information.

---

# Multi-Tenant SaaS Awareness

SaaS systems must enforce tenant isolation.

Examples:

/organizations/{orgId}/projects
/organizations/{orgId}/members

Rules:

* data must be scoped to tenant
* cross-tenant access must be prevented
* authorization must include tenant checks

---

# Observability and Monitoring

Endpoints must support operational visibility.

Recommended practices:

* structured logging
* correlation IDs
* request tracing
* performance metrics

Log events should include:

* endpoint
* user or tenant id
* status code
* execution time

---

# Performance Considerations

Endpoints should minimize expensive operations.

Best practices:

* avoid N+1 database queries
* implement caching when appropriate
* limit response payload size
* paginate large collections

---

# Rate Limiting

Public APIs must implement rate limiting.

Examples:

* requests per minute per user
* requests per minute per API key
* burst limits

Rate limiting protects infrastructure from abuse.

---

# Output Format

When applying this skill, the agent must produce:

1. Endpoint definition
2. Request schema
3. Validation rules
4. Response schema
5. Security considerations
6. Multi-tenant considerations
7. Implementation outline
