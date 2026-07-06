# VEOS Configuration

Controls engineering preferences and behavior.

Configuration adjusts decisions.

Core principles remain unchanged.

---

# Mode

Default:

balanced

Available modes:

* strict
* balanced
* lightweight

---

# Strict Mode

Use for:

* enterprise systems
* production applications
* large teams

Behavior:

* stronger reviews
* more documentation
* deeper validation

---

# Balanced Mode

Default mode.

Use for:

* most professional projects

Behavior:

* practical structure
* maintainability focus
* avoid overengineering

---

# Lightweight Mode

Use for:

* prototypes
* experiments
* small tools

Behavior:

* fewer layers
* faster development
* simple structure

---

# Architecture Preferences

Default:

simple_first = true

Meaning:

Start simple.

Increase complexity only when needed.

---

# Existing Project Preference

Default:

respect_existing = true

Rules:

* follow current patterns
* avoid unnecessary rewrites
* preserve behavior

---

# Backend Preferences

Default:

backend_style = practical

Priorities:

1. Correctness

2. Maintainability

3. Security

4. Performance

---

# FastAPI Preferences

Default structure:

api/

schemas/

models/

crud/

core/

---

# FastAPI API Versioning

Default:

enabled

Example:

api/v1/

Use for maintainable APIs.

---

# FastAPI Schemas

Default:

explicit

Use:

* request schemas
* response schemas
* validation

---

# FastAPI Documentation

Default:

enabled

Use:

json_schema_extra

when examples improve API clarity.

---

# FastAPI CRUD Layer

Default:

enabled_when_useful

Use CRUD for:

* database operations
* reusable queries

Avoid empty wrappers.

---

# FastAPI Service Layer

Default:

optional

Create services only for:

* business workflows
* external integrations
* multiple operations

---

# Exception Handling

Default:

custom_exceptions_enabled

Use:

* clear application errors
* centralized handling
* safe responses

---

# Django Preferences

Default:

django_native

Rules:

* follow Django conventions
* use apps properly
* avoid unnecessary patterns

---

# Database Preferences

Default:

data_safety_first

Priorities:

1. Correctness

2. Integrity

3. Query performance

4. Scaling

---

# Security Preferences

Default:

security_by_default

Always consider:

* authentication
* authorization
* secrets
* sensitive data

---

# Dependency Preferences

Default:

minimal_dependencies

Before adding:

Check existing tools.

---

# Testing Preferences

Default:

meaningful_tests

Prioritize:

* business logic
* APIs
* permissions
* failures

---

# Documentation Preferences

Default:

useful_docs_only

Document:

* decisions
* setup
* important behavior

Avoid documentation noise.

---

# Refactoring Preferences

Default:

incremental

Rules:

* preserve behavior
* small improvements
* avoid rewrites

---

# Code Review Preferences

Default:

impact_based

Priority:

1. Bugs

2. Security

3. Data safety

4. Maintainability

5. Style

---

# Performance Preferences

Default:

measure_first

Optimize based on evidence.

Avoid premature scaling.

---

# AI Creativity

Default:

controlled

AI may suggest improvements.

AI must not ignore project constraints.

---

# Final Principle

Configuration changes preferences.

Engineering principles stay consistent.