---

name: external-api-integration-pattern
description: Define safe and reliable patterns for integrating SaaS backend systems with external APIs and services.
category: backend
version: 1.0
---            
# External API Integration Pattern

## Purpose

Provide a structured approach for integrating backend systems with external services and APIs.

External integrations introduce network dependencies and potential failures, which must be handled carefully.

This pattern ensures external services are accessed safely and reliably.

---

# When to Use This Skill

Use this skill whenever:

* calling third-party APIs
* integrating payment providers
* sending emails through external services
* consuming external data services
* receiving webhooks

External services must always be treated as unreliable dependencies.

---

# Core Integration Principles

External services may fail due to:

network issues
timeouts
rate limits
service downtime

Systems must handle these failures gracefully.

---

# Isolation of Integration Logic

External API logic should be isolated in dedicated integration modules or services.

Example structure:

Controller
↓
Service
↓
External Service Client

External API calls must never be scattered across the codebase.

---

# Timeout Configuration

All external requests must enforce timeouts.

Without timeouts, requests may block indefinitely.

Example strategy:

Maximum request time defined per external service.

Requests exceeding this limit must fail safely.

---

# Retry Strategy

Temporary failures may require retry logic.

Recommended retry mechanisms:

limited retry attempts
exponential backoff
jitter delays

Retry loops must always have maximum limits.

---

# Circuit Breaker Pattern

Systems should implement protection against failing external services.

Example behavior:

External API fails repeatedly
↓
Circuit breaker opens
↓
Requests temporarily blocked
↓
System avoids cascading failures

This prevents external outages from bringing down the entire system.

---

# Webhook Handling

Some external systems communicate through webhooks.

Webhook endpoints must:

verify request authenticity
validate payload structure
handle retries safely

Webhooks should be processed asynchronously when possible.

---

# Data Validation

External responses must be validated before use.

External systems may return:

unexpected formats
missing fields
partial responses

All responses must be validated before entering the system.

---

# Observability

External integrations must be observable.

Logs should include:

external service name
request duration
response status
failure reason

Monitoring helps detect external dependency issues.

---

# SaaS Considerations

External integrations may depend on tenant-specific credentials.

Examples:

organization-specific API keys
tenant-specific configuration

Integration logic must support tenant-aware configurations.

---

# Security Considerations

Sensitive credentials must be handled securely.

Examples:

API keys
tokens
secret credentials

Secrets must be stored securely and never exposed in logs.

---

# Output Format

When applying this skill, the agent must produce:

1. External integration architecture
2. Service client structure
3. Retry strategy
4. Timeout configuration
5. Error handling strategy
