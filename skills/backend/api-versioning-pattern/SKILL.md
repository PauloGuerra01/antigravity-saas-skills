---

name: api-versioning-pattern
description: Define strategies for versioning APIs to allow safe evolution of SaaS backend systems without breaking existing clients.
category: backend
version: 1.0
---

# API Versioning Pattern

## Purpose

Enable backend APIs to evolve safely while maintaining compatibility with existing clients.

API versioning allows new features, changes and improvements to be introduced without breaking applications that depend on older API behavior.

This is essential for stable SaaS platforms.

---

# When to Use This Skill

Use this skill whenever:

* modifying existing API contracts
* introducing breaking changes
* evolving response structures
* updating endpoint behavior

Versioning should be planned early in API design.

---

# Versioning Strategies

Common API versioning strategies include:

URL Versioning

Example:

/api/v1/users
/api/v2/users

This is the most common and explicit approach.

---

Header Versioning

Version specified in request headers.

Example:

API-Version: v2

---

Query Parameter Versioning

Example:

/users?version=v2

This approach is less common and generally discouraged.

---

# Recommended Strategy

URL versioning is the most predictable and developer-friendly approach.

Example API structure:

/api/v1/...
/api/v2/...

New versions should introduce improved behavior while preserving older endpoints.

---

# Backward Compatibility

Whenever possible, APIs should maintain backward compatibility.

Strategies include:

adding new optional fields
introducing new endpoints instead of modifying existing ones
supporting both old and new formats during transitions

Breaking changes should be avoided unless necessary.

---

# Deprecation Policy

Older API versions may eventually be deprecated.

Deprecation should follow a clear policy.

Example lifecycle:

Version released
↓
Deprecation announced
↓
Migration period provided
↓
Version retired

Clients must receive advance notice before deprecation.

---

# Documentation

Each API version must have clear documentation.

Documentation should include:

supported endpoints
request formats
response structures
version-specific changes

Good documentation reduces integration issues.

---

# Version Isolation

Different API versions should isolate changes to avoid unintended side effects.

Example structure:

ControllerV1
ControllerV2

Services may be shared when possible.

---

# Testing

Each API version must be tested independently.

Testing should ensure:

older versions still function
new versions behave correctly
changes do not break existing integrations

Regression testing is critical.

---

# Monitoring Version Usage

The system should monitor which API versions clients use.

Metrics should include:

requests per version
error rates per version
deprecated version usage

These metrics help guide deprecation decisions.

---

# Output Format

When applying this skill, the agent must produce:

1. API versioning strategy
2. Versioned endpoint structure
3. Backward compatibility plan
4. Deprecation strategy
5. Monitoring considerations
