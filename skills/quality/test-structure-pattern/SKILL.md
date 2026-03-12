---
name: test-structure-pattern
description: Defines standards for organizing and structuring automated tests within SaaS codebases.
category: quality
version: 1.0
---

# Test Structure Pattern

## Purpose

Ensure automated tests are organized in a consistent and maintainable structure.

A clear test structure improves readability, maintainability and long-term scalability of the testing suite.

Well-structured tests help developers quickly understand what is being validated and how the system behaves.

---

# When to Use This Skill

Use this skill whenever:

- writing new automated tests
- organizing test directories
- refactoring existing test suites
- establishing testing standards in the project

Consistent test organization is essential for large codebases.

---

# Test Directory Structure

Tests should follow a predictable directory structure.

Common approaches include:

placing tests alongside source files  
or maintaining dedicated test directories

Example structure:

src/
  services/
  controllers/

tests/
  unit/
  integration/
  e2e/

Organized test directories make navigation easier.

---

# Naming Conventions

Test files should follow clear naming conventions.

Examples include:

user.service.test.ts  
auth.controller.spec.ts

Names should clearly indicate the component being tested.

Consistent naming improves discoverability.

---

# Test Isolation

Tests should be isolated from each other.

Each test must run independently without relying on shared state.

Isolation prevents hidden dependencies and ensures reliable test execution.

---

# Use of Mocks

External dependencies should be mocked when necessary.

Examples include:

external APIs  
database calls  
message queues

Mocks allow tests to focus on the logic being validated.

---

# Test Readability

Tests should be easy to read and understand.

A common structure includes:

setup phase  
execution phase  
assertion phase

Readable tests help developers quickly understand system behavior.

---

# Test Data Management

Test data should be controlled and predictable.

Examples include:

test fixtures  
factory functions  
mock datasets

Predictable data improves test stability.

---

# Avoiding Test Duplication

Test suites should avoid duplicating logic.

Reusable helpers and utilities may be created to simplify common testing patterns.

This keeps test code clean and maintainable.

---

# Continuous Integration Compatibility

Test structures should support automated execution in CI pipelines.

Tests must run reliably in automated environments.

CI compatibility ensures testing becomes part of the development workflow.

---

# Output Format

When applying this skill, the agent must produce:

1. Test directory structure  
2. Naming convention rules  
3. Test isolation strategy  
4. Mocking approach  
5. Test data management strategy
