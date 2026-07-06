# API Security

APIs expose application functionality.

Every API endpoint is a security boundary.

Design APIs defensively.

---

# API Security Philosophy

APIs should:

* validate input
* protect data
* enforce access
* fail safely

Never trust external requests.

---

# Existing API Rule

Existing API security patterns have priority.

Before changing:

Understand:

* authentication
* permissions
* clients
* compatibility requirements

Do not redesign API security unnecessarily.

---

# Validate All Input

Every external value is untrusted.

Validate:

* request body
* query parameters
* headers
* uploaded files

before processing.

---

# Schema Validation

Use schema validation when possible.

Examples:

* Pydantic
* DRF serializers
* validation libraries

Avoid manual validation everywhere.

---

# Reject Invalid Data

Do not silently accept bad input.

Fail clearly.

Fail safely.

---

# Output Control

Only return required data.

Avoid exposing:

* internal fields
* secrets
* system information

---

# Avoid Overexposure

Bad:

Returning complete database objects.

Good:

Return explicit API responses.

APIs are contracts.

---

# Authentication

Protected endpoints require identity verification.

Do not depend on frontend restrictions.

Backend must enforce security.

---

# Authorization

Every sensitive action requires permission checks.

Verify:

* role
* ownership
* allowed actions

---

# Rate Limiting

Protect endpoints from abuse.

Consider limits for:

* login
* search
* expensive operations
* public APIs

---

# Request Size Limits

Restrict large requests.

Protect against:

* resource exhaustion
* accidental overload

---

# File Upload Security

Validate:

* file type
* file size
* permissions

Never trust uploaded content.

---

# Error Responses

Errors should be useful but safe.

Avoid exposing:

* stack traces
* database details
* infrastructure information

---

# HTTP Methods

Use methods correctly.

Examples:

GET:

retrieve

POST:

create/action

PUT/PATCH:

update

DELETE:

remove

---

# HTTPS

Production APIs should use encrypted communication.

Protect data in transit.

---

# CORS

Configure CORS intentionally.

Avoid:

allow everything

unless truly required.

---

# Headers

Use security headers when appropriate.

Examples:

* content security controls
* browser protections

Based on application type.

---

# API Versioning

Version APIs when compatibility matters.

Avoid breaking existing clients unexpectedly.

---

# Pagination

Large responses should use pagination.

Avoid unlimited data exposure.

---

# Filtering And Sorting

Validate user-controlled filters.

Prevent:

* expensive queries
* unintended access

---

# Webhooks

Treat webhooks as external input.

Verify:

* signatures
* sources
* payloads

---

# Internal APIs

Internal does not mean trusted.

Protect service communication.

---

# Sensitive Operations

Extra care for:

* payments
* account changes
* permissions
* data exports

---

# Logging APIs

Log useful information.

Never log:

* passwords
* tokens
* private data

---

# Testing API Security

Test:

* unauthorized requests
* invalid input
* permission failures
* edge cases

---

# Warning Signs

Review APIs when:

* frontend controls security
* responses expose full models
* permissions are missing
* errors expose internals

---

# API Security Checklist

Before completion:

[ ] Input validated

[ ] Output controlled

[ ] Authentication applied

[ ] Authorization checked

[ ] Errors are safe

[ ] Sensitive data protected

---

# Final Principle

Every API endpoint is an entrance.

Protect every entrance intentionally.