---
name: code-review-quality-pattern
description: Defines standards and best practices for performing effective code reviews in SaaS development.
category: quality
version: 1.0
---

# Code Review Quality Pattern

## Purpose

Ensure that all code changes are reviewed before being merged into the main codebase.

Code reviews help identify architectural issues, security risks and maintainability concerns before code reaches production.

They also improve knowledge sharing across the development team.

---

# When to Use This Skill

Use this skill whenever:

- submitting pull requests
- reviewing feature implementations
- evaluating architectural changes
- validating critical bug fixes

Code reviews should be part of every change that affects the codebase.

---

# Review Scope

Reviewers should evaluate multiple aspects of the proposed changes.

Examples include:

code correctness  
architecture alignment  
readability and maintainability  
performance considerations  
security implications

Reviews should focus on system quality rather than personal coding preferences.

---

# Pull Request Guidelines

Code reviews typically occur through pull requests.

Pull requests should include:

clear description of the change  
reference to related tasks or issues  
explanation of architectural decisions

Well-described changes improve review efficiency.

---

# Review Size

Smaller changes are easier to review effectively.

Large pull requests increase the risk of overlooked issues.

Changes should be broken into smaller logical units whenever possible.

---

# Reviewer Responsibility

Reviewers are responsible for ensuring that changes meet project standards.

Responsibilities include:

verifying test coverage  
checking adherence to coding standards  
identifying potential bugs

Constructive feedback should guide improvements.

---

# Author Responsibility

The author of the code should:

respond to review comments  
clarify implementation details  
apply necessary fixes

Collaboration between author and reviewer improves code quality.

---

# Avoiding Superficial Reviews

Reviews should not be rushed.

Superficial approvals increase the risk of defects entering production.

Reviewers should understand the purpose and impact of the change.

---

# Continuous Improvement

Code reviews should also identify opportunities to improve system design.

Examples include:

refactoring opportunities  
simplifying complex logic  
improving documentation

Reviews contribute to long-term system quality.

---

# Output Format

When applying this skill, the agent must produce:

1. Code review guidelines  
2. Pull request structure  
3. Review evaluation checklist  
4. Collaboration workflow  
5. Quality improvement considerations
