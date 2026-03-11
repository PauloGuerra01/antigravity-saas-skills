---

name: repository-pattern
description: Organize database access through repositories to isolate persistence logic from business logic in SaaS backends.
category: backend
version: 1.0
---

# Repository Pattern

## Purpose

Ensure database access is isolated in dedicated repository classes or modules.
This pattern separates persistence concerns from business logic and prevents services or controllers from directly interacting with the database layer.

Benefits:

* maintainable data access layer
* improved testability
* easier database migrations
* reusable query logic
* better separation of concerns

---

# When to Use This Skill

Use this skill whenever:

* implementing database queries
* reading or writing persistent data
* interacting with relational or document databases
* building SaaS backend modules that require persistence

Typical resources include:

* users
* organizations
* subscriptions
* invoices
* projects
* tasks

---

# Core Principle

Services must not contain raw database queries.

Instead:

Controller
↓
Service
↓
Repository
↓
Database

Repositories act as the **single interface** between application logic and the persistence layer.

---

# Repository Responsibilities

Repositories are responsible for:

* fetching records
* inserting data
* updating entities
* deleting entities
* mapping database results into domain objects

Repositories should expose **clear and predictable methods**.

Example:

UserRepository

* findById(id)
* findByEmail(email)
* create(userData)
* update(userId, data)
* delete(userId)

---

# What Repositories Must NOT Do

Repositories must not contain:

* business rules
* authorization logic
* workflow orchestration
* service-level validations

Those responsibilities belong to the service layer.

---

# Query Design Guidelines

Queries should be:

* efficient
* indexed
* predictable
* reusable

Avoid:

* duplicated queries
* unnecessary joins
* excessive database calls

Prefer batching operations when possible.

---

# Data Mapping

Repositories should convert database rows into domain-friendly objects.

Example transformation:

Database record:

```json
{
  "user_id": 12,
  "created_at": "2024-01-01"
}
```

Domain object:

```json
{
  "id": 12,
  "createdAt": "2024-01-01"
}
```

Repositories should hide database-specific naming conventions.

---

# Transaction Handling

When multiple writes must succeed together, the service layer should initiate a transaction and repositories should participate in it.

Example flow:

Create order
↓
Insert order record
↓
Insert order items
↓
Commit transaction

If any step fails, the transaction must rollback.

---

# SaaS Data Isolation

Repositories must enforce tenant-aware queries.

Examples:

findProjectsByOrganization(orgId)

getUsersByTenant(tenantId)

Queries must always scope data to the correct tenant.

---

# Performance Considerations

Repositories should help prevent common database performance problems.

Recommended practices:

* use indexes on frequently queried columns
* avoid N+1 queries
* paginate large result sets
* cache expensive queries when appropriate

---

# Testability

Repositories should be easy to mock or replace during testing.

Testing strategy:

* unit tests for services using mocked repositories
* integration tests for repository implementations

---

# Output Format

When applying this skill, the agent should produce:

1. Repository interface definition
2. Example repository methods
3. Example service using the repository
4. Example query implementation
5. Performance considerations
