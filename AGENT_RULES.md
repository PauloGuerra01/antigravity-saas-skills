# Agent Rules

AI agents operating in this repository must follow these rules.

## Rule 1 — Always consult skills first
Before implementing any feature, identify whether a relevant skill exists.

If a skill exists, its rules must guide the implementation.

## Rule 2 — Skills override default behavior
If a skill defines a pattern that conflicts with the agent's default approach, the skill takes priority.

## Rule 3 — Avoid ad-hoc architecture
Do not invent architectural patterns when a skill already defines the correct approach.

## Rule 4 — Respect system layers
Implement changes within the appropriate system layer:
- backend
- frontend
- devops
- quality
- product

## Rule 5 — Maintain consistency
Generated code must follow the conventions defined by the skills.

Inconsistent implementations should be avoided.
