# Backend Standards

Backend systems are responsible for protecting business logic, data, security and reliability.

A backend should be boring, predictable and trustworthy.

---

# Backend Philosophy

A good backend system should be:

* correct
* secure
* maintainable
* observable
* reliable

Advanced patterns do not create good systems.

Good decisions create good systems.

---

# Understand Before Coding

Before implementing backend changes:

Understand:

* existing architecture
* current data flow
* business rules
* failure scenarios

Do not modify behavior without understanding impact.

---

# Existing Backend Rule

Existing backend structure has priority.

When modifying existing projects:

Follow existing:

* folder organization
* naming conventions
* framework patterns
* error handling style

Do not introduce new structures unless required.

Consistency protects maintainability.

---

# New Backend Rule

For new backend projects:

Create clear separation between:

* request handling
* business logic
* data access
* external communication
* configuration

Start simple.

Grow structure only when needed.

---

# Responsibility Separation

Each part of the backend should have a clear purpose.

Avoid mixing:

API handling

*

Business logic

*

Database queries

*

External services

in one place.

Separation should improve understanding.

Not increase file count.

---

# Request Handling

Request layers should:

* validate incoming data
* authenticate users
* call application logic
* format responses

Avoid placing complex business rules here.

---

# Business Logic

Business rules should be:

* explicit
* testable
* independent from transport layer

Avoid coupling business logic directly to:

* HTTP requests
* framework objects
* database details

---

# Data Access

Database interaction should be:

* predictable
* safe
* optimized when needed

Avoid:

* duplicated complex queries
* uncontrolled database access
* hidden side effects

---

# Configuration Management

Configuration must come from environment.

Never hardcode:

* secrets
* credentials
* environment URLs
* deployment values

Different environments require different configuration.

---

# Validation

Validate data at system boundaries.

Validate:

* user input
* external API responses
* file uploads
* configuration values

Never trust external data.

---

# Error Handling

Errors should:

* provide useful context
* be logged appropriately
* protect internal details

Avoid:

* silent failures
* swallowed exceptions
* exposing stack traces

---

# Logging

Logs should explain system behavior.

Good logs answer:

What happened?

Where?

Why?

With what context?

Never log sensitive data.

---

# Security Defaults

Every backend should consider:

* authentication
* authorization
* input validation
* data protection
* dependency security

Security is not optional.

---

# Database Usage

Protect data integrity.

Prefer:

* transactions when needed
* constraints
* migrations
* predictable schemas

Application code should not compensate for poor data design.

---

# External Integrations

External systems fail.

Always handle:

* timeouts
* retries
* unexpected responses
* unavailable services

Never assume external reliability.

---

# Background Processing

Move operations away from requests when:

* execution is slow
* retries are needed
* user does not need immediate result

Background systems require monitoring.

---

# Dependency Management

Before adding packages:

Ask:

* is this necessary?
* is it maintained?
* is it secure?
* does it reduce complexity?

Every dependency becomes ownership.

---

# Performance

Performance improvements require evidence.

Do not optimize blindly.

Process:

1. Measure

2. Find bottleneck

3. Improve

4. Verify

---

# Testing Expectations

Prioritize testing:

* business rules
* critical workflows
* integrations
* failure scenarios

Tests should protect behavior.

---

# Code Review Expectations

Review backend changes for:

* correctness
* security
* maintainability
* simplicity
* production impact

Style is secondary.

---

# Backend Warning Signs

Investigate when:

* simple changes touch many files
* business logic is duplicated
* errors disappear silently
* nobody understands a module
* adding features becomes risky

---

# Backend Checklist

Before completing backend work:

[ ] Existing patterns respected

[ ] Business rules are clear

[ ] Inputs validated

[ ] Permissions checked

[ ] Errors handled

[ ] Logs added where useful

[ ] Data integrity protected

[ ] Tests updated if needed

---

# Final Principle

The best backend code is not noticed.

It quietly handles requests, protects data and survives production.