---

name: authentication-authorization-pattern
description: Implement secure authentication and authorization mechanisms for SaaS backends using token-based identity and role-based access control.
category: backend
version: 1.0
---

# Authentication and Authorization Pattern

## Purpose

Define secure mechanisms to identify users and control access to protected resources in SaaS systems.

Authentication verifies **who the user is**.

Authorization verifies **what the user is allowed to do**.

These mechanisms are critical for protecting application data and enforcing permission rules.

---

# When to Use This Skill

Use this skill whenever:

* implementing user login
* protecting API endpoints
* verifying identity
* enforcing permission rules
* building multi-user SaaS systems

All protected routes must enforce authentication and authorization checks.

---

# Authentication Principles

Authentication ensures that requests originate from verified users.

Common mechanisms:

* email and password login
* token-based authentication
* OAuth providers
* API keys for service integrations

Authentication systems must avoid storing sensitive credentials in plain text.

Passwords must be hashed using strong algorithms.

---

# Token-Based Authentication

Modern SaaS backends typically use token-based authentication.

Common token strategies include:

* JWT tokens
* session tokens
* refresh tokens

Typical flow:

User logs in
↓
Server validates credentials
↓
Server issues access token
↓
Client sends token with each request

Example header:

Authorization: Bearer <token>

---

# Token Security Rules

Tokens must follow strict security rules.

Recommended practices:

* short expiration time
* refresh token rotation
* token signature verification
* secure storage on client side

Tokens must never be exposed in logs.

---

# Authorization Principles

Authorization determines which actions an authenticated user may perform.

Typical models include:

Role-Based Access Control (RBAC)

Examples:

* admin
* member
* viewer

Permission-Based Access

Examples:

* can_create_project
* can_manage_users
* can_view_reports

Authorization must be checked before performing sensitive operations.

---

# Middleware Enforcement

Authentication and authorization should be enforced using middleware.

Example flow:

Request
↓
Authentication Middleware
↓
Authorization Middleware
↓
Controller

This ensures consistent protection across endpoints.

---

# Multi-Tenant SaaS Considerations

SaaS systems must isolate user data by tenant.

Examples:

User belongs to organization
Organization owns projects
Projects contain tasks

Authorization must ensure:

* users only access resources within their organization
* cross-tenant access is prevented

---

# Permission Evaluation

Before executing protected operations, the system must evaluate:

* user identity
* user role
* tenant ownership
* specific permission rules

Example:

A user cannot delete projects owned by another organization.

---

# Security Best Practices

Authentication systems must follow strong security practices.

Recommended protections include:

* password hashing
* login rate limiting
* account lockout after repeated failures
* secure token storage
* HTTPS-only communication

Sensitive operations should require additional verification when necessary.

---

# Audit Logging

Authentication and authorization events should be logged.

Important events include:

* login attempts
* failed authentication
* permission violations
* sensitive actions

Logs help detect security incidents.

---

# Output Format

When applying this skill, the agent must produce:

1. Authentication flow description
2. Token management strategy
3. Authorization model definition
4. Middleware architecture
5. Security considerations
6. Example protected endpoint
