---

name: configuration-management-pattern
description: Define a structured approach for managing environment configuration and secrets in SaaS backend systems.
category: backend
version: 1.0
---

# Configuration Management Pattern

## Purpose

Provide a consistent and secure strategy for managing application configuration across different environments.

Configuration management ensures that environment-specific settings remain separate from application code.

This improves security, portability and operational reliability.

---

# When to Use This Skill

Use this skill whenever:

* configuring environment variables
* managing API credentials
* defining service endpoints
* setting infrastructure parameters
* handling environment-specific behavior

Configuration must never be hardcoded into application logic.

---

# Environment Separation

Applications should support multiple environments.

Typical environments include:

development
staging
production

Each environment should have its own configuration values.

This prevents production secrets from being used in development systems.

---

# Environment Variables

Environment variables are the preferred mechanism for configuration.

Examples:

DATABASE_URL
REDIS_URL
PAYMENT_PROVIDER_API_KEY
EMAIL_SERVICE_KEY

Environment variables allow configuration to be injected at runtime.

---

# Secrets Management

Sensitive credentials must be handled securely.

Examples of secrets include:

API keys
database passwords
authentication tokens
encryption keys

Secrets must never be stored directly in source code.

They should be stored in secure secret management systems when possible.

---

# Configuration Modules

Configuration values should be centralized in dedicated configuration modules.

Example structure:

Application
↓
Configuration Module
↓
Environment Variables

This prevents configuration logic from being scattered across the codebase.

---

# Validation of Configuration

Configuration values must be validated during application startup.

Validation may include:

required variables present
correct data types
valid URLs or identifiers

If configuration validation fails, the application should fail fast.

---

# Default Values

Some configuration values may define safe defaults.

Examples:

request timeout values
cache expiration time
logging levels

Defaults must never override security-sensitive settings.

---

# Feature Flags

Configuration systems may support feature flags.

Feature flags allow:

enabling or disabling features
gradual feature rollout
experimentation with new functionality

Feature flags must be configurable per environment.

---

# SaaS Multi-Tenant Considerations

Some configuration values may vary per tenant.

Examples:

tenant-specific API credentials
tenant configuration flags

The system should support tenant-aware configuration when required.

---

# Security Considerations

Configuration values must be protected from unauthorized access.

Sensitive values must never appear in:

source code
public logs
client responses

Access to configuration systems should be restricted.

---

# Output Format

When applying this skill, the agent must produce:

1. Configuration architecture
2. Environment variable structure
3. Secret management strategy
4. Configuration validation rules
5. Example configuration module
