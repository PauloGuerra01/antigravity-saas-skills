---
name: environment-infrastructure-pattern
description: Define infrastructure environment separation and configuration practices for SaaS systems.
category: devops
version: 1.0
---

# Environment Infrastructure Pattern

## Purpose

Ensure that SaaS systems operate across clearly separated environments.

Each environment must have its own infrastructure and configuration.

This separation prevents development changes from affecting production systems.

---

# When to Use This Skill

Use this skill whenever:

- setting up infrastructure environments
- configuring deployment pipelines
- defining application configuration
- managing infrastructure resources

Environment separation is fundamental for safe software delivery.

---

# Standard Environments

Most SaaS systems use at least three environments.

Development  
Used by engineers during active development.

Staging  
A pre-production environment used to validate changes before release.

Production  
The live environment serving real users.

Each environment must operate independently.

---

# Infrastructure Isolation

Each environment must have its own infrastructure resources.

Examples include:

databases  
caches  
message queues  
storage systems

Production infrastructure must never share resources with development systems.

---

# Configuration Differences

Environment-specific configuration may include:

API endpoints  
database connections  
feature flags  
logging levels

These values should be injected through environment configuration systems.

---

# Deployment Targets

Deployments should follow environment progression.

Typical workflow:

Code pushed to repository  
↓  
Deployed to development environment  
↓  
Validated in staging environment  
↓  
Released to production

This progression reduces deployment risks.

---

# Data Protection

Production data must never be used in development environments.

If production data is required for testing:

data should be anonymized or masked.

Protecting user data is critical for security and compliance.

---

# Infrastructure Scaling

Different environments may require different infrastructure sizes.

Examples:

Development → minimal resources  
Staging → production-like resources  
Production → scalable infrastructure

This allows efficient resource usage.

---

# Access Control

Access to environments must be restricted.

Example policies:

developers → development access  
QA teams → staging access  
operations team → production access

Strict access control protects critical infrastructure.

---

# Monitoring Environments

Monitoring systems should track each environment independently.

Metrics include:

system health  
error rates  
resource usage

Monitoring helps detect issues before they affect production users.

---

# Output Format

When applying this skill, the agent must produce:

1. Environment architecture overview  
2. Infrastructure separation plan  
3. Configuration strategy  
4. Deployment progression strategy  
5. Monitoring and access control rules
