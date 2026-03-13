---

name: rate-limiting-pattern
description: Define a rate limiting strategy to protect SaaS APIs from abuse, brute force attacks and resource exhaustion.
category: backend
version: 1.0
---

# Rate Limiting Pattern

## Purpose

Protect backend APIs from excessive usage, abuse, and denial-of-service scenarios by enforcing request rate limits.

Rate limiting ensures system stability and fair usage of resources in multi-user SaaS environments.

---

# When to Use This Skill

Use this skill whenever:

* exposing public API endpoints
* implementing authentication endpoints
* protecting expensive operations
* preventing brute-force login attempts
* enforcing fair API usage

All externally accessible endpoints should consider rate limiting.

---

# Core Principles

## 1. Prevent Resource Abuse

Without rate limiting, malicious or poorly designed clients can:

* overload servers
* consume excessive database resources
* cause service instability

Rate limiting ensures that no client can overwhelm the system.

---

# Rate Limiting Strategies

Common strategies include:

Fixed Window

Requests are limited within a fixed time window.

Example:

100 requests per minute.

---

Sliding Window

Tracks request frequency continuously and adjusts limits dynamically.

Provides smoother enforcement.

---

Token Bucket

Clients receive tokens representing request capacity.

Each request consumes a token.

Tokens refill over time.

---

# Limiting Dimensions

Rate limits may apply to different identifiers:

Per User
Per IP Address
Per API Key
Per Organization

Example:

User → 60 requests per minute
API Key → 120 requests per minute

---

# Sensitive Endpoint Protection

Some endpoints require stricter limits.

Examples:

Login endpoints
Password reset endpoints
Account creation endpoints

Example rule:

Login attempts limited to 5 per minute.

---

# Response When Limit Is Exceeded

When the rate limit is exceeded, the API must return a clear response.

Example:

```json
{
  "success": false,
  "error": {
    "code": "RATE_LIMIT_EXCEEDED",
    "message": "Too many requests. Please try again later."
  }
}
```

HTTP Status Code:

429 Too Many Requests

---

# Rate Limit Headers

Responses should include rate limit metadata.

Examples:

X-RateLimit-Limit
X-RateLimit-Remaining
X-RateLimit-Reset

These headers help clients understand usage limits.

---

# Distributed Systems Considerations

In distributed environments, rate limits should be stored in shared systems such as:

* Redis
* distributed caches
* centralized API gateways

This ensures consistent limits across multiple servers.

---

# SaaS Plan-Based Limits

Rate limits may vary based on subscription plans.

Example:

Free Plan → 60 requests per minute
Pro Plan → 300 requests per minute
Enterprise → custom limits

This allows scaling API capacity according to plan tiers.

---

# Monitoring and Alerts

Rate limiting systems should be monitored.

Metrics include:

* blocked requests
* rate limit violations
* endpoint usage patterns

These metrics help identify abuse and system bottlenecks.

---

# Output Format

When applying this skill, the agent must produce:

1. Rate limiting strategy definition
2. Endpoint protection rules
3. Example middleware implementation
4. Rate limit headers
5. Monitoring considerations
