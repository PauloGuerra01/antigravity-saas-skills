---

name: webhook-processing-pattern
description: Define secure and reliable patterns for processing incoming webhooks from external services in SaaS backend systems.
category: backend
version: 1.0
---

# Webhook Processing Pattern

## Purpose

Provide a secure and reliable method for receiving and processing webhook events from external services.

Webhooks allow external systems to notify the application about events that occur outside the system.

Proper webhook handling prevents duplicated actions, security vulnerabilities and inconsistent data.

---

# When to Use This Skill

Use this skill whenever:

* receiving webhook events from third-party services
* processing payment notifications
* handling subscription updates
* receiving asynchronous event notifications

Webhook endpoints must be designed for reliability and security.

---

# Webhook Endpoint Design

Webhook endpoints should be dedicated routes.

Example:

POST /webhooks/payment-provider

Webhook endpoints should not share logic with public API endpoints.

They should be isolated and minimal.

---

# Signature Verification

Webhook requests must be verified to ensure they originate from trusted providers.

Common methods include:

HMAC signatures
signed headers
shared secret verification

Requests failing verification must be rejected.

---

# Idempotent Processing

Webhook events may be delivered multiple times.

Processing must be idempotent.

Example:

Payment confirmation event received twice
↓
System processes event only once

Event identifiers should be stored to prevent duplicate processing.

---

# Asynchronous Processing

Webhook processing should not block HTTP responses.

Recommended flow:

Receive webhook
↓
Validate request
↓
Store event
↓
Queue background job
↓
Process event asynchronously

This ensures reliability and faster responses.

---

# Event Logging

Webhook events should be logged for traceability.

Logs should include:

event identifier
provider name
timestamp
processing status

Logs help investigate failed or duplicated events.

---

# Failure Handling

Webhook processing may fail due to temporary errors.

Recommended strategies include:

retry mechanisms
dead-letter queues
manual recovery tools

Failed events must be tracked and retried safely.

---

# Security Considerations

Webhook endpoints should enforce strict security rules.

Examples:

IP allowlists
signature verification
payload validation

Webhook endpoints must not expose sensitive internal information.

---

# SaaS Multi-Tenant Considerations

Webhook events may reference tenant-specific resources.

Examples:

subscription updates
billing events
organization usage events

Webhook processing must ensure events are mapped to the correct tenant.

---

# Monitoring and Alerts

Webhook systems should be monitored.

Important metrics include:

failed event processing
duplicate events
queue backlog

Alerts should notify operators when webhook processing fails repeatedly.

---

# Output Format

When applying this skill, the agent must produce:

1. Webhook endpoint design
2. Signature verification strategy
3. Idempotent processing mechanism
4. Asynchronous processing architecture
5. Monitoring and failure handling strategy
