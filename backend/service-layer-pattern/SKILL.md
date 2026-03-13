---
name: service-layer-pattern
description: Enforce a layered backend architecture separating controllers, services and data access layers for scalable SaaS systems.
category: backend
version: 1.0
---

# Service Layer Pattern

## Purpose

Ensure backend systems follow a clean layered architecture by separating responsibilities between controllers, services and repositories.

This pattern improves:

* maintainability
* testability
* scalability
* code organization

The agent must avoid placing business logic in controllers or routes.

---

# When to Use This Skill

Use this skill whenever:

* implementing backend features
* writing API controllers
* creating business logic
* interacting with databases
* building SaaS backend modules

---

# Core Architecture

The backend must follow this structure:

Route
↓
Controller
↓
Service
↓
Repository / Data Access

Each layer has a clear responsibility.

---

# Layer Responsibilities

## Routes

Responsibilities:

* define HTTP endpoints
* map routes to controllers
* apply middleware (auth, validation, rate limiting)

Routes must not contain business logic.

Example:

```
POST /users
GET /projects/{id}
```

---

## Controllers

Controllers are responsible for:

* receiving requests
* validating inputs
* calling services
* formatting responses

Controllers should remain thin.

They must not:

* implement business logic
* access the database directly
* contain complex conditional logic

---

## Services

Services contain the **core business logic**.

Responsibilities:

* domain logic
* workflows
* orchestration of multiple repositories
* business validations
* transaction coordination

Examples:

UserService
BillingService
SubscriptionService
ProjectService

Services should be reusable across controllers.

---

## Repositories

Repositories are responsible for:

* database access
* queries
* persistence logic

Responsibilities include:

* fetching records
* inserting data
* updating records
* deleting records

Repositories must not contain business logic.

---

# Dependency Flow

Dependencies must always flow downward.

Allowed:

Controller → Service
Service → Repository

Not allowed:

Controller → Repository
Repository → Controller
Service → Controller

This prevents architectural coupling.

---

# Transaction Management

When operations require multiple database changes, services should control transactions.

Example:

Create subscription
↓
Create billing record
↓
Update account status

All steps must succeed or rollback.

---

# Validation Strategy

Validation occurs at multiple layers.

Controller level:

* request format
* required fields
* basic schema validation

Service level:

* business rules
* domain constraints
* authorization checks

---

# Reusability Principles

Services should be reusable.

Avoid duplicating logic across controllers.

Example:

Bad:

UserController implements password rules

Good:

PasswordService handles password validation.

---

# Testability

Each layer should be independently testable.

Testing strategy:

Controller tests
Service unit tests
Repository integration tests

This structure simplifies automated testing.

---

# SaaS Architecture Considerations

Services must enforce SaaS rules such as:

* tenant isolation
* permission checks
* usage limits
* feature access by subscription plan

Examples:

OrganizationService
SubscriptionService
UsageLimitService

---

# Performance Considerations

Services should:

* minimize database calls
* batch operations when possible
* avoid repeated queries
* use caching strategies where appropriate

---

# Output Format

When applying this skill, the agent must produce:

1. Route definition
2. Controller outline
3. Service implementation plan
4. Repository structure
5. Data flow explanation
6. Example implementation
