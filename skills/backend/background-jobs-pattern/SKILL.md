---

name: background-jobs-pattern
description: Define patterns for handling asynchronous background jobs in SaaS backend systems.
category: backend
version: 1.0
---

# Background Jobs Pattern

## Purpose

Ensure long-running or non-critical operations are executed asynchronously instead of blocking API requests.

Background jobs improve system responsiveness and reliability by moving heavy tasks outside the request-response cycle.

This pattern is essential for scalable SaaS systems.

---

# When to Use This Skill

Use this skill whenever:

* operations take significant time
* external APIs are involved
* large data processing occurs
* notifications or emails are sent
* batch operations are executed

These tasks should not run inside synchronous API requests.

---

# Common Background Job Examples

Typical background tasks include:

sending emails
processing payments
generating reports
processing uploaded files
syncing external APIs
generating analytics data

Moving these tasks to background workers improves API performance.

---

# Asynchronous Processing Flow

Typical job processing flow:

API Request
↓
Service triggers job creation
↓
Job added to queue
↓
Worker processes job asynchronously

This allows the API to return a response immediately.

---

# Job Queue Systems

Background jobs are typically managed by queue systems.

Examples include:

message queues
task queues
job schedulers

Queues allow reliable distribution of work across multiple workers.

---

# Job Payload Design

Jobs should contain minimal necessary information.

Example payload:

```json
{
  "jobType": "SEND_EMAIL",
  "userId": "user_123",
  "template": "welcome_email"
}
```

Payloads should avoid including large data structures.

Workers should retrieve necessary data from the database.

---

# Retry Strategy

Background jobs should support retry mechanisms.

Temporary failures may occur due to:

network errors
external service downtime
database locks

Retry strategies should include:

retry limits
exponential backoff
failure logging

---

# Idempotency

Background jobs should be designed to run safely multiple times.

This prevents duplicated actions if retries occur.

Example:

Sending duplicate billing charges must be avoided.

Systems should check whether the action was already executed.

---

# Failure Handling

Failed jobs must be handled safely.

Strategies include:

retry queues
dead-letter queues
manual investigation workflows

Critical failures should trigger alerts.

---

# Monitoring Job Systems

Job processing systems should be monitored.

Important metrics include:

queue length
processing time
failure rate
retry rate

Monitoring helps identify bottlenecks and system failures.

---

# SaaS Considerations

In multi-tenant systems, background jobs must include tenant context.

Example:

organizationId
tenantId

This ensures jobs operate within the correct tenant boundaries.

---

# Output Format

When applying this skill, the agent must produce:

1. Background job architecture
2. Job payload structure
3. Queue processing flow
4. Retry strategy
5. Monitoring considerations
