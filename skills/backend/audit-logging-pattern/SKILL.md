---

name: audit-logging-pattern
description: Define an audit logging strategy to track important actions performed by users in SaaS systems.
category: backend
version: 1.0
---

# Audit Logging Pattern

## Purpose

Ensure important actions performed in the system are recorded for traceability, security and operational analysis.

Audit logs provide a historical record of user actions and system events.

They help identify:

* unauthorized activity
* system misuse
* operational errors
* data changes

---

# When to Use This Skill

Use this skill whenever:

* users modify critical data
* system configuration changes occur
* sensitive operations are executed
* administrative actions are performed
* security-related events happen

Audit logs should be recorded for all sensitive operations.

---

# What Should Be Logged

Audit logs should capture meaningful events.

Examples include:

User account creation
Password changes
Role changes
Permission updates
Billing modifications
Subscription changes
Deletion of resources
Administrative actions

Not every request needs an audit log.

Only meaningful state changes should be recorded.

---

# Audit Log Structure

Audit logs should follow a consistent structure.

Example:

```json
{
  "event": "USER_CREATED",
  "actorId": "user_123",
  "targetId": "user_456",
  "organizationId": "org_789",
  "timestamp": "2024-01-01T12:00:00Z",
  "metadata": {}
}
```

Fields explanation:

event → action performed
actorId → who performed the action
targetId → entity affected
organizationId → tenant context
timestamp → when the event occurred

Metadata may contain additional context.

---

# Separation from System Logs

Audit logs must be separate from application logs.

Application logs:

* debugging
* performance monitoring
* internal errors

Audit logs:

* user activity
* security events
* data changes

Mixing both types can make investigations difficult.

---

# Immutability

Audit logs must be immutable.

Rules:

* logs must not be edited
* logs must not be deleted
* corrections should generate new entries

This ensures historical accuracy.

---

# Security Considerations

Audit logs may contain sensitive data.

Recommended practices:

* restrict access to logs
* encrypt sensitive fields
* protect logs from tampering

Audit logs must never expose passwords or secret tokens.

---

# SaaS Multi-Tenant Considerations

In multi-tenant SaaS environments, audit logs must include tenant context.

Example:

organizationId
tenantId

This ensures logs can be filtered by organization.

---

# Storage Strategies

Audit logs may be stored in:

* dedicated database tables
* log management systems
* event streams
* security monitoring platforms

The storage system should support long-term retention.

---

# Monitoring and Investigation

Audit logs should enable investigation of system activity.

Common investigation scenarios:

* who deleted a project
* who modified billing settings
* who granted administrative privileges
* when a subscription was changed

Logs should allow filtering by:

* user
* event type
* time range
* organization

---

# Output Format

When applying this skill, the agent must produce:

1. Audit event definition
2. Logging strategy
3. Audit log data structure
4. Example logging implementation
5. Security and retention considerations
