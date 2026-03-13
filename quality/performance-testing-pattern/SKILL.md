---
name: performance-testing-pattern
description: Defines performance testing practices to evaluate scalability, response time and system stability in SaaS applications.
category: quality
version: 1.0
---

# Performance Testing Pattern

## Purpose

Ensure that the system can handle expected user traffic and operational workloads without degradation in performance.

Performance testing identifies bottlenecks and scalability limits before the system is exposed to real-world traffic.

This helps maintain responsive and reliable SaaS applications.

---

# When to Use This Skill

Use this skill whenever:

- preparing for production releases
- validating scalability of critical endpoints
- analyzing system performance under load
- testing infrastructure capacity

Performance testing is essential for systems expected to scale.

---

# Types of Performance Tests

Different testing approaches evaluate different aspects of performance.

Load Testing  
Simulates expected levels of user traffic to evaluate normal system behavior.

Stress Testing  
Pushes the system beyond its limits to observe failure conditions.

Spike Testing  
Simulates sudden increases in traffic to observe system stability.

These tests reveal system behavior under various conditions.

---

# Performance Metrics

Performance tests should measure key metrics.

Examples include:

response time  
throughput  
error rate  
resource usage

These metrics provide insights into system performance and scalability.

---

# Test Environment

Performance tests should be executed in environments similar to production.

This ensures realistic results.

Differences in infrastructure can significantly affect performance outcomes.

---

# Identifying Bottlenecks

Performance tests help detect bottlenecks in system components.

Examples include:

database queries  
API endpoints  
external integrations  
resource-intensive processes

Identifying bottlenecks enables targeted optimization.

---

# Performance Baselines

Establishing baseline performance metrics helps track improvements or regressions over time.

Baselines provide reference points for evaluating future system changes.

---

# Continuous Performance Testing

Performance tests may be integrated into development workflows.

Regular performance validation ensures that new changes do not degrade system performance.

Continuous monitoring complements periodic testing.

---

# Output Format

When applying this skill, the agent must produce:

1. Performance testing strategy  
2. Types of tests to be executed  
3. Metrics to monitor  
4. Bottleneck analysis approach  
5. Performance baseline definition
