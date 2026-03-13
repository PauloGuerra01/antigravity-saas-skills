---

name: caching-strategy-pattern
description: Define caching strategies to improve performance and reduce database load in SaaS backend systems.
category: backend
version: 1.0
---

# Caching Strategy Pattern

## Purpose

Improve backend performance by reducing repeated database queries and expensive computations through effective caching strategies.

Caching reduces system latency and infrastructure load by storing frequently accessed data in fast-access storage.

This is especially important in SaaS systems where many users request similar data repeatedly.

---

# When to Use This Skill

Use this skill whenever:

* endpoints frequently access the same data
* database queries are expensive
* data is read much more often than it is written
* high request volumes are expected

Caching should be applied carefully to avoid stale data issues.

---

# Common Caching Layers

Caching may exist at different layers of the system.

Application Cache
Cache stored directly in the application process.

Distributed Cache
Shared cache used across multiple server instances.

Examples include:

Redis
Memcached

Edge Cache
Caching performed by API gateways or CDNs.

---

# Cacheable Data

Common SaaS data that can benefit from caching:

configuration settings
public resource lists
feature flags
pricing plans
organization metadata
dashboard statistics

Highly dynamic or sensitive data should not be cached.

---

# Cache Invalidation

Cache invalidation is critical for maintaining data accuracy.

Strategies include:

Time-Based Expiration (TTL)

Cached data expires after a predefined time.

Example:

Cache expires after 5 minutes.

---

Event-Based Invalidation

Cache is cleared when underlying data changes.

Example:

User updates profile
↓
User profile cache invalidated

---

# Cache Key Design

Cache keys must uniquely identify stored data.

Example:

user:123
organization:456:projects
dashboard:stats:org_789

Keys should be predictable and consistent.

---

# Avoiding Cache Stampede

A cache stampede occurs when many requests try to rebuild a cache simultaneously.

Strategies to prevent this include:

staggered expiration
background refresh
locking mechanisms

These techniques protect the database during high traffic.

---

# Multi-Tenant SaaS Considerations

In SaaS systems, cache keys must include tenant identifiers.

Example:

organization:123:projects

This prevents data leakage across tenants.

---

# Security Considerations

Cached data must respect security rules.

Avoid caching:

sensitive personal data
authentication tokens
payment information

Caches must not expose data across users or organizations.

---

# Monitoring Cache Performance

Cache systems should be monitored for:

hit rate
miss rate
eviction rate
memory usage

Low cache hit rates may indicate poor cache strategy.

---

# Output Format

When applying this skill, the agent must produce:

1. Cache strategy definition
2. Cache key structure
3. Cache invalidation rules
4. Example cache implementation
5. Monitoring considerations
