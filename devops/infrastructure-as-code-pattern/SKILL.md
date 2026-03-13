---
name: infrastructure-as-code-pattern
description: Define infrastructure as code practices for managing SaaS infrastructure through version-controlled configuration.
category: devops
version: 1.0
---

# Infrastructure as Code Pattern

## Purpose

Ensure infrastructure is defined and managed through version-controlled code rather than manual configuration.

Infrastructure as Code (IaC) allows teams to provision and manage infrastructure in a consistent and reproducible way.

This approach improves reliability, transparency and automation.

---

# When to Use This Skill

Use this skill whenever:

- provisioning servers
- configuring networking
- deploying cloud resources
- managing infrastructure environments

All infrastructure changes should be implemented through code.

---

# Core Concept

Infrastructure definitions should be stored in code repositories.

Examples of infrastructure elements defined through code:

servers  
databases  
network configurations  
load balancers  
storage systems

Version-controlled infrastructure ensures every change is traceable.

---

# Benefits of Infrastructure as Code

Infrastructure as Code provides several advantages:

reproducible environments  
version history for infrastructure changes  
automated infrastructure provisioning  
reduced configuration drift

These benefits improve operational stability.

---

# Infrastructure Version Control

Infrastructure definitions should be stored alongside application code or in dedicated infrastructure repositories.

Changes to infrastructure should follow the same workflow as application code:

code change  
↓  
review process  
↓  
automated deployment

This ensures infrastructure updates are controlled and auditable.

---

# Automated Provisioning

Infrastructure provisioning should be automated.

Example workflow:

infrastructure configuration defined in code  
↓  
automation tool applies configuration  
↓  
cloud resources created or updated

Manual infrastructure creation should be avoided.

---

# Environment Consistency

Infrastructure definitions should support multiple environments.

Examples include:

development  
staging  
production

Each environment should be provisioned using the same infrastructure code.

This ensures environments remain consistent.

---

# Change Management

Infrastructure changes should be reviewed before deployment.

Review processes help detect:

security risks  
misconfigurations  
resource conflicts

This prevents infrastructure-related incidents.

---

# Monitoring Infrastructure

Infrastructure resources must be monitored after deployment.

Monitoring should track:

resource usage  
availability  
performance metrics

Monitoring helps maintain system reliability.

---

# Security Considerations

Infrastructure code must follow security best practices.

Examples include:

restricting network access  
protecting sensitive configuration values  
limiting privileged access

Security must be integrated into infrastructure design.

---

# Output Format

When applying this skill, the agent must produce:

1. Infrastructure architecture overview  
2. Infrastructure code structure  
3. Automated provisioning workflow  
4. Environment consistency strategy  
5. Security and monitoring considerations
