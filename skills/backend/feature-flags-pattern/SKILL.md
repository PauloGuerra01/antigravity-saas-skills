---

name: feature-flags-pattern
description: Define a strategy for controlling application features dynamically using feature flags in SaaS systems.
category: backend
version: 1.0
---

# Feature Flags Pattern

## Purpose

Allow features to be enabled or disabled dynamically without requiring a new deployment.

Feature flags provide a mechanism to control functionality in production environments safely.

This enables controlled rollouts, experimentation and fast recovery from feature-related issues.

---

# When to Use This Skill

Use this skill whenever:

* introducing new features
* performing gradual rollouts
* testing functionality in production
* enabling experimental features
* disabling problematic features quickly

Feature flags allow features to exist in code without being immediately visible to all users.

---

# Feature Flag Architecture

Feature flags should be evaluated through a centralized feature flag service.

Example architecture:

Application
↓
Feature Flag Service
↓
Feature Evaluation Logic

This ensures feature decisions remain consistent across the system.

---

# Feature Flag Types

Common types of feature flags include:

Release Flags
Used to gradually roll out new features.

Experiment Flags
Used for A/B testing and experimentation.

Operational Flags
Used to enable or disable system behavior during incidents.

Permission Flags
Used to control access to premium or restricted features.

---

# Targeting Strategies

Feature flags may target specific users or groups.

Examples:

specific users
specific organizations
subscription plans
percentage of traffic

Example rollout strategy:

Enable feature for 5% of users
↓
Increase to 25%
↓
Increase to 100%

---

# Evaluation Location

Feature flag evaluation should occur at the service or application layer.

Example:

Service checks whether a feature is enabled before executing logic.

This keeps feature decisions centralized.

---

# Safe Feature Rollouts

New features should be released gradually.

Recommended rollout strategy:

deploy code with feature disabled
↓
enable feature for internal users
↓
enable for small percentage of users
↓
enable globally after validation

Gradual rollout reduces risk.

---

# Feature Flag Cleanup

Feature flags should not remain permanently in the codebase.

Once a feature is stable:

* remove the flag
* simplify the code
* remove conditional logic

This prevents long-term technical debt.

---

# SaaS Multi-Tenant Considerations

Feature flags may be applied at different levels:

global
organization-level
subscription-plan-level

Example:

Enterprise plan users receive early access to new features.

---

# Monitoring Feature Impact

Feature rollouts should be monitored.

Metrics may include:

error rate
performance impact
user adoption
feature usage

Monitoring ensures features behave as expected.

---

# Output Format

When applying this skill, the agent must produce:

1. Feature flag architecture
2. Flag evaluation logic
3. Rollout strategy
4. Monitoring approach
5. Feature cleanup plan
