---
name: security-testing-pattern
description: Defines security testing practices to detect vulnerabilities and protect SaaS applications from security threats.
category: quality
version: 1.0
---

# Security Testing Pattern

## Purpose

Ensure that the application is evaluated for potential security vulnerabilities.

Security testing identifies weaknesses that could expose sensitive data or allow unauthorized access.

Protecting system integrity and user information is a fundamental requirement for SaaS applications.

---

# When to Use This Skill

Use this skill whenever:

- releasing new features
- modifying authentication mechanisms
- integrating external services
- validating production readiness

Security testing should be performed regularly throughout the development lifecycle.

---

# Common Security Risks

Security testing should focus on detecting common vulnerabilities.

Examples include:

injection attacks  
authentication bypass  
improper access control  
sensitive data exposure

Identifying these risks early helps prevent exploitation.

---

# Input Validation Testing

Applications should validate all external input.

Tests should verify that the system safely handles:

user input  
API parameters  
file uploads  
external integrations

Proper validation prevents many common attacks.

---

# Authentication and Authorization Testing

Security tests should confirm that authentication mechanisms work correctly.

Examples include:

verifying session handling  
ensuring role-based access control  
preventing privilege escalation

Access control must always enforce correct permissions.

---

# Dependency Security

Applications often rely on external libraries.

Security testing should include scanning dependencies for known vulnerabilities.

Keeping dependencies updated reduces exposure to known security risks.

---

# Automated Security Scanning

Security scanning tools can detect vulnerabilities automatically.

Examples include:

dependency vulnerability scanning  
static security analysis  
configuration security checks

Automated tools help maintain continuous security monitoring.

---

# Penetration Testing

Periodic penetration testing may be performed to simulate real-world attack scenarios.

Penetration testing helps identify complex vulnerabilities that automated tools may miss.

---

# Incident Preparedness

Security testing should also support incident response readiness.

Teams should be prepared to respond quickly if vulnerabilities are discovered.

Preparedness improves response time during real security incidents.

---

# Output Format

When applying this skill, the agent must produce:

1. Security testing strategy  
2. Vulnerability assessment approach  
3. Authentication and authorization test plan  
4. Dependency scanning strategy  
5. Incident preparedness considerations
