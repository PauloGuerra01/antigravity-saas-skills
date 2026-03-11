---

name: input-validation-pattern
description: Enforce strict input validation rules for backend APIs to ensure data integrity and security in SaaS systems.
category: backend
version: 1.0

---

# Input Validation Pattern

## Purpose

Ensure all external input entering the backend system is validated before reaching business logic.

This prevents:

* malformed data
* injection vulnerabilities
* unexpected runtime errors
* inconsistent database states

Validation is a critical security and reliability mechanism for production SaaS systems.

---

# When to Use This Skill

Use this skill whenever:

* receiving HTTP requests
* processing user input
* handling query parameters
* accepting JSON request bodies
* processing file uploads
* interacting with external APIs

All untrusted input must be validated.

---

# Core Principles

## 1. Never Trust Client Input

Clients can send any data, including:

* invalid types
* missing fields
* malicious payloads
* oversized requests

Every request must be validated before processing.

---

# Validation Layers

Validation should occur at two levels.

Controller Level

Responsibilities:

* schema validation
* required fields
* type validation
* request format validation

Example:

* email format
* password length
* numeric fields

---

Service Level

Responsibilities:

* business rules
* domain constraints
* cross-entity validation

Examples:

* user must belong to organization
* subscription plan must exist
* feature must be enabled

---

# Schema Validation

Use a schema-driven validation approach.

Examples of schema rules:

Required fields

email: string
password: string
organizationId: uuid

Optional fields

displayName: string

Type enforcement

age: integer
price: number

---

# Sanitization

Input should be sanitized before use.

Examples:

* trim whitespace
* normalize email addresses
* remove dangerous characters

Never store unsanitized user input.

---

# Error Response Standard

Validation failures must return structured errors.

Example response:

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid request payload"
  }
}
```

Avoid exposing internal validation details.

---

# Payload Size Limits

Endpoints should enforce payload limits.

Examples:

* request body size
* number of items in arrays
* file upload size

Large payloads can lead to denial-of-service risks.

---

# Security Considerations

Validation helps prevent:

* SQL injection
* NoSQL injection
* command injection
* malformed payload attacks

All input must be treated as untrusted.

---

# SaaS Considerations

Validation must respect SaaS constraints such as:

* tenant identifiers
* organization ownership
* plan limitations

Example rule:

A user cannot create resources outside their organization.

---

# Logging and Monitoring

Validation failures should be logged for security monitoring.

Logs should include:

* endpoint
* user identifier
* validation error code

Sensitive data must not be logged.

---

# Output Format

When applying this skill, the agent must produce:

1. Request validation schema
2. Controller validation logic
3. Service-level validation rules
4. Example validation error response
5. Security considerations
