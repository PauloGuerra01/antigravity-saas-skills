---

name: containerization-pattern
description: Define containerization practices for packaging and running SaaS applications consistently across environments.
category: devops
version: 1.0
---

# Containerization Pattern

## Purpose

Ensure applications are packaged in containers so they can run consistently across development, testing and production environments.

Containerization isolates application dependencies and system configurations.

This prevents environment-specific issues and improves deployment reliability.

---

# When to Use This Skill

Use this skill whenever:

* packaging backend services
* packaging frontend applications
* preparing applications for cloud deployment
* creating reproducible environments

Containerization simplifies infrastructure management.

---

# Container Basics

Containers bundle the application with its runtime dependencies.

A container includes:

application code
runtime environment
system libraries
configuration

This allows the container to run consistently on any compatible system.

---

# Container Images

Applications should be packaged as container images.

Images are immutable artifacts that represent a specific version of the application.

Example build flow:

Source Code
↓
Dockerfile
↓
Build Container Image

Images should be versioned and stored in container registries.

---

# Dockerfile Structure

A Dockerfile defines how the container image is built.

Typical steps include:

select base image
install dependencies
copy application code
define startup command

Dockerfiles should be simple and optimized.

---

# Image Optimization

Container images should be optimized for performance and security.

Best practices include:

using lightweight base images
removing unnecessary files
minimizing image layers

Smaller images improve build speed and deployment efficiency.

---

# Multi-Container Systems

SaaS applications often run multiple containers.

Examples include:

frontend container
backend API container
database container
cache container

Each service should run in its own container.

---

# Container Networking

Containers communicate through defined network interfaces.

Services should communicate using internal service names or networking layers.

Direct host dependencies should be avoided.

---

# Configuration Management

Containers should not store environment-specific configuration inside the image.

Configuration should be injected at runtime using:

environment variables
configuration services

This keeps images reusable across environments.

---

# Security Considerations

Containers must follow security best practices.

Examples include:

running applications as non-root users
limiting container privileges
keeping base images updated

Security scanning should be applied to container images.

---

# Output Format

When applying this skill, the agent must produce:

1. Containerization architecture
2. Dockerfile structure
3. Image build strategy
4. Multi-container service structure
5. Security and optimization considerations
