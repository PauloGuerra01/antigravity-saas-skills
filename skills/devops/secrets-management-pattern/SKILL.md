---
name: secrets-management-pattern
description: Defines secure practices for managing sensitive credentials and secrets in SaaS systems.
category: devops
version: 1.0
---

# Secrets Management Pattern

## Purpose

Ensure sensitive credentials are stored, accessed and managed securely across all environments.

Secrets include any data that must remain confidential to protect system integrity and user data.

Proper secrets management prevents accidental exposure of critical credentials.

---

# When to Use This Skill

Use this skill whenever:

- storing API keys
- managing database credentials
- handling authentication tokens
- configuring third-party integrations

Sensitive credentials must never be stored directly in source code.

---

# Types of Secrets

Common secrets include:

database passwords  
API keys  
private encryption keys  
authentication tokens  
service credentials

All secrets must be treated as confidential assets.

---

# Secret Storage

Secrets should be stored in secure secret management systems.

Examples include:

environment secret stores  
secret management services  
encrypted configuration stores

Secrets should not be stored in plaintext configuration files.

---

# Secret Injection

Secrets should be injected into applications at runtime.

Common injection methods include:

environment variables  
secure configuration services  
container runtime configuration

Applications should read secrets only when needed.

---

# Access Control

Access to secrets must follow strict permission rules.

Example policies:

applications → access only required secrets  
developers → limited access in development environments  
operations teams → restricted production access

Principle of least privilege should always be applied.

---

# Secret Rotation

Secrets should be rotated periodically.

Rotation reduces the risk of long-term exposure.

Example rotation scenarios:

database credential updates  
API key renewal  
token regeneration

Rotation policies should be automated when possible.

---

# Secret Auditing

Access to secrets should be logged and audited.

Logs should track:

who accessed a secret  
when it was accessed  
which system used it

Auditing helps detect unauthorized access.

---

# Environment Separation

Secrets must be separated by environment.

Examples:

development secrets  
staging secrets  
production secrets

Production credentials must never be shared with development systems.

---

# Security Considerations

Secrets must never appear in:

source code repositories  
application logs  
error messages  
client-side code

Strict controls must protect all secret values.

---

# Output Format

When applying this skill, the agent must produce:

1. Secrets storage strategy  
2. Secret injection mechanism  
3. Access control policies  
4. Secret rotation process  
5. Auditing and monitoring practices
