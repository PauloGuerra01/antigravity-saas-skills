See `00_AI_CONTEXT.md` for AI agent instructions.

# Skill Routing Guide

This file helps AI agents quickly determine which engineering skills should be consulted when solving development tasks.

Agents should consult the relevant skill category before generating implementation code.

---

# Backend Tasks

If the task involves:

- API endpoints
- database access
- services
- background jobs
- authentication
- caching
- webhooks

Consult skills in:

skills/backend/

---

# Frontend Tasks

If the task involves:

- UI components
- state management
- API calls from the client
- frontend architecture
- authentication flows

Consult skills in:

skills/frontend/

---

# Infrastructure / DevOps Tasks

If the task involves:

- deployment
- infrastructure
- CI/CD
- containers
- monitoring
- backups
- environment configuration

Consult skills in:

skills/devops/

---

# Code Quality Tasks

If the task involves:

- automated testing
- test organization
- code reviews
- static analysis
- performance testing
- security validation

Consult skills in:

skills/quality/

---

# Product / Feature Design Tasks

If the task involves:

- feature definition
- product requirements
- SaaS pricing or monetization
- feature validation

Consult skills in:

skills/product/

---

# Important Rule

Before implementing any solution:

1. Identify the system layer affected by the task.
2. Locate the relevant skill category.
3. Read the corresponding SKILL.md file.
4. Follow the architectural constraints defined in the skill.

Avoid implementing solutions that conflict with existing skill definitions.

:::writing{variant=“standard” id=“91247”}

Agent Startup Procedure

Before implementing any change, AI agents must follow this order:
	1.	Read 00_AI_CONTEXT.md to understand the repository.
	2.	Follow the rules defined in AGENT_RULES.md.
	3.	Use SKILL_ROUTING.md to identify the correct skill category.
	4.	Read the relevant SKILL.md file inside the skills/ directory.
	5.	Validate the implementation using SKILL_CHECKLIST.md.

Do not implement features without consulting the relevant skill definitions.
:::
