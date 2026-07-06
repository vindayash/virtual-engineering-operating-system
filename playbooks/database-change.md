# Playbook: Database Change

Database changes require extra care.

Data is often the most valuable part of a system.

Protect it.

---

# Purpose

Modify databases safely while preserving:

* existing data
* application behavior
* system reliability

---

# Active Agents

Use:

* Database Agent
* Backend Agent
* Security Agent
* Architect Agent

---

# Primary Rule

Never change databases blindly.

Understand impact first.

---

# Step 1: Understand Current Database

Analyze:

* database type
* schema
* relationships
* constraints
* usage patterns

Know what exists.

---

# Step 2: Understand Requirement

Identify:

Why is the change needed?

Examples:

* new feature
* performance issue
* data model improvement

---

# Step 3: Analyze Impact

Check:

What depends on this?

Review:

* APIs
* services
* reports
* background jobs
* integrations

---

# Step 4: Choose Change Strategy

Prefer safe evolution.

Examples:

Adding:

Usually safer.

Removing:

Requires more planning.

Changing:

Requires compatibility checks.

---

# Schema Changes

Before modifying schema:

Consider:

* existing records
* migrations
* application compatibility

---

# Migration Planning

A migration should define:

* change being made
* data transformation
* rollback considerations

---

# Production Data Rule

Assume production contains:

* unexpected values
* old records
* edge cases

Handle safely.

---

# Removing Fields

Before removal:

Check:

* usage
* dependencies
* historical data needs

Consider phased removal.

---

# Renaming Fields

Renames can break systems.

Review:

* application code
* APIs
* integrations
* reports

---

# Data Migration

For data transformations:

Consider:

* dataset size
* execution time
* failure recovery

---

# Large Tables

For large datasets:

Avoid:

* locking operations
* massive single transactions

Plan carefully.

---

# Index Changes

Add indexes based on:

* query patterns
* performance evidence

Not automatically.

---

# Relationship Changes

Consider:

* constraints
* cascading behavior
* data consistency

---

# Transaction Safety

Use transactions when:

multiple changes must succeed together.

---

# Backup Awareness

Before risky operations:

Confirm recovery strategy.

---

# Application Compatibility

Plan order:

Database change

*

Application deployment

Avoid breaking running systems.

---

# Security Review

Check:

* sensitive fields
* permissions
* access impact

---

# Testing

Test:

* migration execution
* rollback strategy
* application behavior

---

# Documentation

Record important changes.

Use ADR when architecture changes.

---

# AI Behavior Rule

Claude must explain:

* database impact
* migration concerns
* risks

before major changes.

---

# Avoid

Never automatically:

* drop data
* rewrite schemas
* remove constraints
* change database technology

without strong reason.

---

# Output Format

Return:

## Current Database State

What exists.

## Required Change

What changes.

## Migration Plan

Safe steps.

## Risks

Possible issues.

## Verification

How to confirm success.

---

# Final Principle

Code can be rewritten.

Lost data cannot.

Protect the database.