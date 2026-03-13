---
name: deployment-architecture-pattern
description: Define deployment architecture and environment structure for SaaS applications.
category: devops
version: 1.0
---

# Deployment Architecture Pattern

## Purpose

Provide a structured approach for deploying SaaS applications reliably across multiple environments.

Deployment architecture defines how application components are built, packaged and deployed to infrastructure.

A clear deployment strategy improves reliability, scalability and operational stability.

---

# When to Use This Skill

Use this skill whenever:

- deploying backend services
- deploying frontend applications
- configuring infrastructure environments
- planning production deployments

All SaaS systems must have a predictable and repeatable deployment process.

---

# Environment Structure

Applications should support multiple environments.

Common environments include:

development  
staging  
production  

Each environment must have isolated infrastructure and configuration.

This separation prevents production systems from being affected by development changes.

---

# Build Process

Applications must be built into deployable artifacts.

Examples:

frontend build bundles  
backend application builds  
container images  

Build processes must be automated and reproducible.

Manual builds should be avoided.

---

# Containerization

Applications should be packaged in containers when possible.

Containerization provides:

environment consistency  
portable deployments  
simplified scaling

Containers ensure applications behave the same across environments.

---

# Deployment Flow

Typical deployment flow:

Source Code  
↓  
Build Pipeline  
↓  
Artifact Creation  
↓  
Deployment to Environment  

Automated pipelines should handle this process.

---

# Rolling Deployments

Production deployments should avoid downtime.

Recommended strategy:

rolling deployments

Example flow:

deploy new version to subset of instances  
↓  
monitor system behavior  
↓  
gradually replace old instances

This reduces risk during updates.

---

# Rollback Strategy

Deployments must support rollback.

If a new deployment introduces issues:

previous version must be restored quickly.

Rollback capability is essential for production safety.

---

# Infrastructure Separation

Application components should be separated.

Examples:

frontend hosting  
backend services  
databases  
caches

This separation improves scalability and operational control.

---

# Monitoring Deployments

Deployments must be monitored.

Important signals include:

error rates  
response latency  
resource usage  

Monitoring helps detect problems immediately after deployment.

---

# Security Considerations

Deployment systems must protect sensitive credentials.

Examples include:

deployment keys  
environment secrets  
infrastructure credentials

Access to deployment systems must be restricted.

---

# Output Format

When applying this skill, the agent must produce:

1. Deployment architecture overview  
2. Environment structure  
3. Build and packaging strategy  
4. Deployment flow  
5. Rollback and monitoring strategy
