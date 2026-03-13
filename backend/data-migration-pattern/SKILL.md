---

name: data-migration-pattern
description: Define safe database migration strategies for evolving SaaS backend systems without data loss or downtime.
category: backend
version: 1.0
---

# Data Migration Pattern

## Purpose

Provide a structured approach for evolving database schemas and data structures safely as the system grows.

Database migrations ensure that structural changes to the database are applied consistently across environments.

This prevents schema drift and reduces the risk of production failures.

---

# When to Use This Skill

Use this skill whenever:

* creating new database tables
* modifying existing schema structures
* changing column types
* adding indexes
* transforming existing data

All database changes should be implemented through migration scripts.

---

# Migration Versioning

Database migrations must be versioned.

Each migration represents a single incremental change.

Example sequence:

Migration 001 → create users table
Migration 002 → add email index
Migration 003 → add subscription table

Versioned migrations allow systems to track schema evolution.

---

# Migration Principles

Migrations should follow these principles:

small incremental changes
clear ordering
reproducible execution

Each migration must be deterministic.

Running migrations on different environments must produce identical results.

---

# Forward-Only Migrations

In production systems, migrations should typically be forward-only.

This means:

new migrations move the schema forward

Rollback should be used cautiously, especially when data transformations are involved.

---

# Data Transformation

Some migrations require transforming existing data.

Examples:

splitting columns
renaming fields
restructuring tables

Data migrations must include safe transformation logic.

These transformations must be tested carefully before production deployment.

---

# Backward Compatibility

During deployments, application code and database schema must remain temporarily compatible.

Strategies include:

add new columns before removing old ones
support both schema versions during transition

This prevents failures during rolling deployments.

---

# Index Management

Migrations should include index management.

Indexes improve query performance but may affect write performance.

Common index use cases:

frequently filtered columns
foreign keys
search fields

Indexes should be applied carefully to avoid performance degradation.

---

# Testing Migrations

Migration scripts must be tested before production use.

Testing should verify:

schema updates succeed
data remains intact
queries still function correctly

Migration testing helps prevent deployment failures.

---

# Production Safety

Production migrations must consider system availability.

Recommended strategies:

apply migrations during low traffic periods
monitor system behavior during migration
avoid long-running blocking operations

Large migrations should be performed gradually when possible.

---

# SaaS Multi-Tenant Considerations

In multi-tenant systems, migrations must ensure all tenant data remains intact.

Migration scripts must never mix or corrupt tenant-specific data.

Data isolation must always be preserved.

---

# Output Format

When applying this skill, the agent must produce:

1. Migration strategy definition
2. Example migration script structure
3. Data transformation considerations
4. Deployment safety strategy
5. Migration testing plan
