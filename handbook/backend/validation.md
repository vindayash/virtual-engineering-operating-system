# Validation

Validation protects systems from invalid data and incorrect behavior.

Every system boundary must verify what enters it.

Never trust external input.

---

# Validation Philosophy

Validation should make systems:

* safer
* predictable
* easier to debug

Validation exists to prevent invalid states.

Not to create unnecessary layers.

---

# Validate At Boundaries

Validate data when it enters the system.

Examples:

* API requests
* external webhooks
* file uploads
* configuration
* third-party responses

External data cannot be trusted.

---

# Existing Project Rule

Existing validation patterns have priority.

When modifying existing systems:

Follow current:

* validation style
* framework conventions
* error format

Do not introduce new validation frameworks unnecessarily.

---

# Validation Responsibility

Different layers protect different things.

Each validation should have a clear purpose.

Avoid duplicating the same validation everywhere.

---

# API Validation

API validation checks:

* required fields
* data types
* formats
* basic constraints

Examples:

* email format
* maximum length
* allowed values

Reject invalid requests early.

---

# Business Validation

Business validation protects rules.

Examples:

A user cannot withdraw more money than available.

An expired coupon cannot be applied.

A cancelled order cannot be shipped.

These are business decisions.

They should not live only in API validation.

---

# Database Validation

Database constraints protect data integrity.

Use:

* required fields
* unique constraints
* foreign keys
* consistency rules

Never rely only on application code for critical integrity.

---

# Avoid Over Validation

Do not validate the same rule everywhere.

Example:

Checking email format:

API layer

*

Service layer

*

Database layer

without reason creates maintenance problems.

---

# Input Sanitization

Handle unsafe input.

Protect against:

* injection attacks
* malformed data
* unexpected formats

Security begins at boundaries.

---

# External API Validation

Never assume third-party responses are correct.

Validate:

* response structure
* required values
* unexpected states

External systems change.

---

# Configuration Validation

Validate application configuration during startup.

Check:

* required variables
* invalid values
* missing settings

Fail early.

Do not fail later in production.

---

# Error Messages

Validation errors should be:

* clear
* helpful
* safe

Good:

"Email format is invalid"

Bad:

"Database field user.email rejected regex validation"

Do not expose internals.

---

# Validation Location

Put validation where ownership belongs.

Question:

Who understands this rule?

The owner of the rule should validate it.

---

# Avoid Generic Validators

Avoid creating:

ValidationManager

CommonValidator

UniversalValidator

that contains unrelated rules.

Group validation by responsibility.

---

# Security Validation

Always validate:

* permissions
* ownership
* access rules

Never trust:

* frontend checks
* hidden fields
* client-provided roles

---

# Validation And Performance

Validation should protect the system.

But avoid:

* unnecessary database calls
* duplicate expensive checks
* repeated external calls

Validate intelligently.

---

# Testing Validation

Test:

* invalid inputs
* boundary cases
* security-sensitive rules
* business restrictions

Failures should be predictable.

---

# Validation Warning Signs

Review validation when:

* rules exist in many places
* nobody knows where validation happens
* invalid states reach the database
* validation hides business logic

---

# Validation Checklist

Before adding validation:

Ask:

[ ] What rule is protected?

[ ] Which layer owns this rule?

[ ] Is this already validated?

[ ] What happens if validation fails?

[ ] Is the error safe?

---

# Final Principle

Good validation prevents impossible states.

It protects the system without making the system harder to understand.