---

name: database-transaction-pattern
description: Define safe transaction handling patterns to maintain data consistency in SaaS backend systems.
category: backend
version: 1.0
---

# Database Transaction Pattern

## Purpose

Ensure that related database operations are executed safely as a single atomic unit.

Transactions prevent inconsistent system states when multiple database changes must occur together.

If any operation fails, the entire transaction must be rolled back.

This guarantees data integrity.

---

# When to Use This Skill

Use this skill whenever:

* multiple database operations depend on each other
* financial or billing operations occur
* data must remain consistent across multiple tables
* system state must not partially update

Transactions are essential for maintaining reliable data.

---

# Atomic Operations

Transactions ensure atomicity.

Atomicity means:

Either all operations succeed
Or none of them are applied

Example scenario:

Create subscription
↓
Create billing record
↓
Activate user features

If billing record creation fails, the subscription must not remain partially created.

---

# Transaction Flow

Typical transaction flow:

Start transaction
↓
Execute database operations
↓
Validate results
↓
Commit transaction

If any operation fails:

Rollback transaction

Rollback restores the previous database state.

---

# Service Layer Responsibility

Transactions should be controlled by the service layer.

Example architecture:

Controller
↓
Service (transaction start)
↓
Repository operations
↓
Commit or rollback

Repositories should not independently manage transactions.

This prevents nested or conflicting transactions.

---

# Avoid Long Transactions

Transactions should remain short.

Long-running transactions can cause:

database locks
performance degradation
deadlocks

Heavy processing should occur outside the transaction when possible.

---

# Idempotency Considerations

Transactional operations should also support idempotency.

This ensures repeated requests do not create duplicate data.

Example:

If a payment creation request is retried, the system should detect the previous transaction.

---

# Concurrency Control

Multiple users may modify the same data simultaneously.

Strategies include:

optimistic locking
pessimistic locking
version fields

These mechanisms prevent conflicting updates.

---

# Error Handling

If an error occurs during a transaction:

The transaction must be rolled back.

All partial changes must be discarded.

Errors should be logged for investigation.

---

# SaaS Multi-Tenant Considerations

Transactions must respect tenant boundaries.

All queries inside a transaction must include tenant context when applicable.

Example:

organizationId
tenantId

This prevents cross-tenant data modification.

---

# Monitoring and Observability

Transaction failures should be monitored.

Metrics may include:

transaction failure rate
deadlock frequency
rollback count

These metrics help detect data integrity issues.

---

# Output Format

When applying this skill, the agent must produce:

1. Transaction boundary definition
2. Service layer transaction flow
3. Example transactional operation
4. Rollback strategy
5. Concurrency handling considerations
