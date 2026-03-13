---

name: observability-monitoring-pattern
description: Define observability practices including structured logging, metrics and tracing for SaaS backend systems.
category: backend
version: 1.0
---

# Observability and Monitoring Pattern

## Purpose

Ensure backend systems provide visibility into their internal behavior through logging, metrics and monitoring.

Observability allows engineers to understand system performance, detect issues early and diagnose production problems.

A production SaaS system must provide insight into:

* request flow
* system health
* error rates
* resource usage

---

# When to Use This Skill

Use this skill whenever:

* building backend services
* exposing APIs
* running distributed systems
* handling production traffic
* diagnosing system failures

Observability must be considered from the beginning of system design.

---

# Core Observability Components

A complete observability system includes three pillars:

Structured Logging
Metrics
Distributed Tracing

These components work together to provide a full picture of system behavior.

---

# Structured Logging

Logs must follow a structured format rather than plain text.

Example structured log:

```json
{
  "level": "error",
  "message": "Database query failed",
  "endpoint": "/projects",
  "userId": "user_123",
  "organizationId": "org_456",
  "timestamp": "2024-01-01T12:00:00Z"
}
```

Structured logs allow systems to filter and analyze logs efficiently.

---

# Logging Guidelines

Logs should include contextual information.

Recommended fields:

requestId
userId
organizationId
endpoint
statusCode
executionTime

Sensitive information must never be logged.

Examples of sensitive data:

passwords
tokens
payment details

---

# Metrics

Metrics measure system performance over time.

Common backend metrics include:

request rate
error rate
response latency
CPU usage
memory usage
database query time

Metrics allow teams to identify performance bottlenecks.

---

# Tracing

Tracing tracks the path of a request through different services.

Example flow:

API Gateway
↓
Authentication Service
↓
Billing Service
↓
Database

Tracing helps diagnose slow or failing requests.

---

# Health Checks

Services should expose health check endpoints.

Example:

GET /health

The health endpoint should verify:

* database connectivity
* cache availability
* external service connectivity

Health checks allow infrastructure systems to detect failures.

---

# Monitoring and Alerts

Monitoring systems should track key metrics and trigger alerts.

Examples of alerts:

high error rate
slow response times
service downtime
database failures

Alerts should notify operators when system health degrades.

---

# SaaS Multi-Tenant Considerations

In SaaS systems, monitoring should include tenant context.

Examples:

organizationId
tenantId

This helps identify whether issues affect specific tenants or the entire platform.

---

# Observability Tools

Observability can be implemented using various tools.

Examples include:

log aggregation systems
metrics monitoring platforms
distributed tracing systems

The specific tools may vary depending on the infrastructure.

---

# Output Format

When applying this skill, the agent must produce:

1. Logging strategy
2. Metrics definition
3. Tracing architecture
4. Monitoring and alerting plan
5. Health check implementation
