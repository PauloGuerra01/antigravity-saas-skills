---
name: monitoring-alerting-pattern
description: Defines monitoring and alerting practices to ensure reliability and operational awareness in SaaS systems.
category: devops
version: 1.0
---

# Monitoring and Alerting Pattern

## Purpose

Ensure system health and performance are continuously observed through monitoring systems.

Monitoring provides visibility into the behavior of applications and infrastructure in real time.

Alerting ensures that operators are notified when abnormal conditions occur.

---

# When to Use This Skill

Use this skill whenever:

- operating production systems
- managing infrastructure resources
- maintaining application reliability
- detecting system failures

Monitoring is essential for maintaining stable SaaS operations.

---

# Key Monitoring Areas

Monitoring should cover several aspects of the system.

Application Metrics  
Track request rates, error rates and response times.

Infrastructure Metrics  
Track CPU usage, memory consumption and network activity.

Database Metrics  
Monitor query performance, connection usage and storage growth.

Observing these metrics helps detect anomalies early.

---

# Logging Integration

Monitoring systems should integrate with application logging.

Logs provide detailed context about system behavior.

Examples include:

application errors  
authentication events  
system warnings

Logs help diagnose issues discovered through monitoring.

---

# Alerting Rules

Alerting systems should trigger notifications when metrics exceed defined thresholds.

Examples include:

high error rate alerts  
increased response latency  
unusual resource consumption

Alerts must indicate conditions requiring investigation.

---

# Alert Severity Levels

Alerts should be categorized by severity.

Example levels include:

informational alerts  
warning alerts  
critical alerts

This helps teams prioritize responses to incidents.

---

# Notification Channels

Alerts must reach responsible operators quickly.

Common notification channels include:

email notifications  
incident management systems  
team communication platforms

Fast notification helps reduce downtime.

---

# Incident Response

Monitoring systems support incident response workflows.

Typical response flow:

alert triggered  
↓  
team investigates issue  
↓  
problem resolved  
↓  
system restored

Monitoring ensures incidents are detected quickly.

---

# Historical Metrics

Monitoring systems should store historical metrics.

Historical data helps identify:

long-term performance trends  
capacity planning needs  
recurring system issues

Trend analysis improves system reliability.

---

# Security Considerations

Monitoring systems must protect sensitive operational data.

Access to monitoring dashboards and logs should be restricted.

Unauthorized access could expose system internals.

---

# Output Format

When applying this skill, the agent must produce:

1. Monitoring architecture overview  
2. Metrics collection strategy  
3. Alerting rule definitions  
4. Incident response workflow  
5. Monitoring security considerations
