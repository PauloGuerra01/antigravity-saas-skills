---
name: backup-recovery-pattern
description: Defines strategies for data backup and recovery to ensure resilience and data protection in SaaS systems.
category: devops
version: 1.0
---

# Backup and Recovery Pattern

## Purpose

Ensure critical system data is protected against loss by implementing reliable backup and recovery strategies.

Backups safeguard application data from accidental deletion, system failures and infrastructure incidents.

A well-defined recovery process ensures services can be restored quickly with minimal disruption.

---

# When to Use This Skill

Use this skill whenever:

- managing production databases
- storing persistent user data
- maintaining application state
- protecting critical system information

Any system storing user or business data must implement backup strategies.

---

# Backup Types

Different types of backups serve different recovery purposes.

Full Backups  
Complete snapshot of all data at a specific time.

Incremental Backups  
Only changes since the last backup are stored.

Differential Backups  
Stores all changes since the last full backup.

Combining these strategies improves efficiency and recovery speed.

---

# Backup Frequency

Backup schedules must be defined based on system requirements.

Examples include:

hourly backups  
daily backups  
weekly archival backups

The frequency depends on how critical and dynamic the stored data is.

---

# Backup Storage

Backups must be stored in reliable and separate locations.

Examples include:

cloud storage systems  
dedicated backup storage services  
remote infrastructure

Backup storage must remain isolated from the primary system.

---

# Data Retention Policies

Backup systems should define retention policies.

Examples:

retain backups for 7 days  
retain weekly backups for 1 month  
retain monthly backups for 1 year

Retention policies balance storage cost and recovery capability.

---

# Recovery Procedures

Recovery procedures must be documented and tested.

Typical recovery steps include:

identify backup version  
restore database snapshot  
verify system integrity  
resume application services

Recovery time objectives should be defined.

---

# Disaster Recovery Planning

Disaster recovery plans define how the system recovers from major incidents.

Examples include:

data center failures  
large-scale infrastructure outages  
security incidents

Systems should support rapid restoration from backups.

---

# Backup Testing

Backup processes must be tested periodically.

Testing ensures:

backups are valid  
recovery processes work correctly  
data integrity is preserved

Untested backups may fail during real incidents.

---

# Security Considerations

Backups may contain sensitive data.

Backup systems must enforce:

encryption of stored backups  
access control policies  
secure transmission of backup data

Protecting backup data is essential for security compliance.

---

# Output Format

When applying this skill, the agent must produce:

1. Backup strategy definition  
2. Backup schedule  
3. Storage and retention policies  
4. Recovery procedures  
5. Disaster recovery considerations
