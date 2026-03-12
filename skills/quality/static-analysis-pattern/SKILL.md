---
name: static-analysis-pattern
description: Defines static code analysis practices to automatically detect quality issues and enforce coding standards.
category: quality
version: 1.0
---

# Static Analysis Pattern

## Purpose

Ensure code quality by automatically analyzing source code for potential issues without executing the program.

Static analysis tools help detect errors, enforce coding standards and identify security risks early in the development process.

Automated analysis improves consistency and reduces defects in the codebase.

---

# When to Use This Skill

Use this skill whenever:

- writing new code
- submitting pull requests
- maintaining large codebases
- enforcing coding standards

Static analysis should run automatically during development and CI pipelines.

---

# Static Analysis Tools

Static analysis tools examine code structure and patterns.

Common types of analysis include:

linting tools  
type checking tools  
security analyzers  
code quality analyzers

These tools help identify problems before runtime.

---

# Linting Rules

Linting enforces consistent coding style and structure.

Examples include:

naming conventions  
code formatting rules  
unused variables  
complexity thresholds

Consistent linting improves readability and maintainability.

---

# Type Safety

Type checking tools verify that values and functions follow defined type rules.

Benefits include:

detecting type mismatches  
preventing runtime errors  
improving code reliability

Strong typing improves long-term maintainability.

---

# Security Analysis

Static analysis tools may also detect potential security issues.

Examples include:

unsafe input handling  
hardcoded secrets  
vulnerable dependencies

Security scanning helps identify risks early.

---

# Integration with CI/CD

Static analysis should run automatically in CI pipelines.

Typical workflow:

code change submitted  
↓  
analysis tools executed  
↓  
issues detected and reported

CI integration ensures code quality standards are enforced.

---

# Rule Configuration

Analysis tools should be configured according to project standards.

Configuration files define:

enabled rules  
severity levels  
ignored patterns

Proper configuration balances strictness and developer productivity.

---

# Continuous Improvement

Static analysis rules may evolve as the project grows.

Teams should periodically review and update analysis configurations.

This helps maintain alignment with evolving best practices.

---

# Output Format

When applying this skill, the agent must produce:

1. Static analysis strategy  
2. Tool configuration guidelines  
3. Linting and type-checking rules  
4. CI integration strategy  
5. Security analysis considerations
