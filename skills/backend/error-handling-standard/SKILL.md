---

name: error-handling-standard
description: Define a consistent and secure error handling strategy for backend APIs in SaaS systems.
category: backend
version: 1.0
---

# Error Handling Standard

## Purpose

Ensure all backend APIs handle errors in a consistent, secure, and predictable way.

A standardized error handling strategy improves:

* debugging
* observability
* security
* frontend integration
* system reliability

All errors should follow a unified structure.

---

# When to Use This Skill

Use this skill whenever:

* handling runtime errors
* processing API requests
* interacting with databases
* calling external services
* validating inputs

All unexpected failures must be captured and handled safely.

---

# Core Principles

## 1. Never Expose Internal Errors

Internal system details must never be returned to clients.

Never expose:

* stack traces
* SQL queries
* internal file paths
* framework errors

Clients should only receive safe and human-readable messages.

---

# Standard Error Response Format

All API errors must follow the same response structure.

Example:

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable error message"
  }
}
```

The error code should represent a machine-readable identifier.

Examples:

USER_NOT_FOUND
INVALID_INPUT
UNAUTHORIZED
RESOURCE_CONFLICT
INTERNAL_ERROR

---

# Error Categories

Errors should be categorized.

Common categories include:

Validation Errors
Authentication Errors
Authorization Errors
Business Logic Errors
Infrastructure Errors

This improves monitoring and debugging.

---

# HTTP Status Codes

Errors must return appropriate HTTP status codes.

Examples:

400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
409 → Conflict
500 → Internal Server Error

Correct status codes help clients interpret failures.

---

# Centralized Error Handling

Error handling should be centralized in a global handler.

Example flow:

Request
↓
Controller
↓
Service
↓
Error Occurs
↓
Global Error Handler
↓
Standardized Response

This prevents duplicated try/catch blocks across the codebase.

---

# Logging Strategy

All errors must be logged internally.

Logs should include:

* error type
* endpoint
* user identifier
* request ID
* timestamp

Sensitive information must never be logged.

---

# Observability Integration

Error handling should integrate with monitoring systems.

Recommended practices:

* structured logging
* error tracking tools
* alerting systems

Critical errors should trigger alerts.

---

# SaaS Considerations

In multi-tenant SaaS environments:

Errors must never expose data from another tenant.

Example:

A user from organization A must not receive error messages containing identifiers from organization B.

---

# Retry Safety

Some operations may be retried safely.

Examples:

* network failures
* temporary service outages

Retry logic should be implemented carefully to avoid duplicated operations.

---

# Output Format

When applying this skill, the agent must produce:

1. Error response structure
2. List of standardized error codes
3. Global error handler outline
4. Logging strategy
5. Example error responses
