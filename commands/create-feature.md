# Command: Create Feature

Add new functionality safely within an existing project.

Extend the system.

Do not unnecessarily rebuild it.

---

# Purpose

Create features that are:

* correct
* maintainable
* secure
* consistent with existing code

---

# Required Behavior

Before writing code:

Understand existing implementation.

Then extend.

Never assume a blank project.

---

# Active Agents

Use:

* Architect Agent
* Backend Agent
* Database Agent
* Security Agent

as required.

---

# Step 1: Understand Requirement

Identify:

* user need
* expected behavior
* inputs
* outputs
* constraints

Build the right thing.

---

# Step 2: Analyze Existing Code

Before implementation:

Check:

* folder structure
* patterns
* framework usage
* naming conventions

Follow the project.

---

# Step 3: Find Similar Features

Look for existing:

* APIs
* models
* services
* utilities
* tests

Match established patterns.

Consistency matters.

---

# Step 4: Choose Minimal Design

Prefer the smallest design that works.

Avoid adding:

* unnecessary layers
* unused abstractions
* new frameworks

Complexity requires reason.

---

# Architecture Rules

Follow:

handbook/architecture/

Do not introduce architecture changes unless required.

---

# Framework Rules

Follow:

handbook/frameworks/

Examples:

FastAPI:

Use project router/schema/service patterns.

Django:

Follow existing app structure.

Flask:

Follow existing blueprint structure.

---

# API Changes

When adding APIs:

Ensure:

* validation exists
* response format matches project
* errors are handled
* permissions are checked

---

# Database Changes

Before changing database:

Consider:

* schema impact
* migrations
* existing data

Follow:

handbook/database/

---

# Security Requirements

Always check:

* authentication
* authorization
* sensitive data
* validation

Follow:

handbook/security/

---

# Service Layer Rule

Only add services when useful.

Valid reasons:

* business workflows
* multiple operations
* external integrations

Avoid empty forwarding services.

---

# Dependency Rule

Before adding packages:

Ask:

Can existing tools solve this?

Add dependencies only with clear value.

---

# Error Handling

Use project error patterns.

Prefer:

* consistent exceptions
* meaningful failures

Do not hide errors.

---

# Testing

Add tests where they provide value.

Prioritize:

* business behavior
* permissions
* failures

Avoid meaningless coverage.

---

# Documentation

Update documentation when:

* behavior changes
* setup changes
* APIs change

Do not document obvious code.

---

# Implementation Order

Recommended:

1. Understand existing code

2. Update models/schema if needed

3. Add business logic

4. Add API layer

5. Add tests

6. Verify behavior

Adjust based on framework.

---

# AI Generation Rule

Claude must generate:

* required changes only
* correct file locations
* project-consistent code

No unrelated cleanup.

---

# Must Avoid

Never automatically:

* restructure project
* replace libraries
* create generic frameworks
* rewrite working modules
* add unused abstractions

---

# Output Format

Provide:

## Understanding

Feature summary.

## Implementation Plan

Files and changes.

## Code Changes

Required modifications only.

## Security Notes

Important considerations.

## Testing

Recommended verification.

---

# Final Principle

A new feature should feel like it always belonged in the project.