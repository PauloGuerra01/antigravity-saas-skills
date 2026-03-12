---
name: ci-cd-pipeline-pattern
description: Define continuous integration and continuous deployment pipelines for automated SaaS application delivery.
category: devops
version: 1.0
---

# CI/CD Pipeline Pattern

## Purpose

Establish an automated pipeline that builds, tests and deploys the application whenever changes are introduced.

CI/CD pipelines reduce manual work, improve code reliability and accelerate delivery of new features.

Automation ensures that deployments follow a consistent and repeatable process.

---

# When to Use This Skill

Use this skill whenever:

- new code is pushed to the repository
- pull requests are created
- builds must be validated
- applications need to be deployed automatically

CI/CD pipelines are essential for modern SaaS development workflows.

---

# Continuous Integration (CI)

Continuous Integration ensures that code changes are automatically validated.

Typical CI steps include:

install dependencies  
run static analysis  
run automated tests  
build application artifacts

CI prevents broken code from reaching production environments.

---

# Continuous Deployment (CD)

Continuous Deployment automates the process of releasing new versions of the application.

Typical CD steps include:

build artifact packaging  
container image creation  
deployment to staging  
deployment to production

Deployment rules may vary depending on project requirements.

---

# Pipeline Stages

A typical pipeline includes several stages.

Example pipeline:

Source Code  
↓  
Build Stage  
↓  
Test Stage  
↓  
Artifact Creation  
↓  
Deployment Stage

Each stage validates the system before progressing to the next.

---

# Branch Strategy

CI/CD pipelines often integrate with branch strategies.

Common branches include:

main  
develop  
feature branches

Example behavior:

feature branches → run tests  
main branch → deploy to production

Branch-based rules improve development workflows.

---

# Quality Gates

Pipelines should include quality gates.

Examples include:

test coverage thresholds  
linting validation  
security checks

If quality gates fail, the pipeline must stop.

This prevents low-quality code from being deployed.

---

# Environment Deployments

Pipelines should deploy code progressively.

Example sequence:

development environment  
↓  
staging environment  
↓  
production environment

This ensures code is validated before reaching production.

---

# Rollback Support

CI/CD systems must support rollback strategies.

If a deployment fails:

previous version must be redeployed.

Rollback capabilities reduce production risks.

---

# Monitoring and Feedback

Pipelines should provide feedback about build and deployment results.

Examples include:

build status notifications  
deployment reports  
failure alerts

Feedback allows teams to quickly detect problems.

---

# Output Format

When applying this skill, the agent must produce:

1. CI/CD pipeline structure  
2. Pipeline stages definition  
3. Branch integration strategy  
4. Quality gate rules  
5. Deployment automation plan
