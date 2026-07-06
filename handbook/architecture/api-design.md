# API Design

APIs are contracts between systems.

A good API is predictable, secure, understandable and difficult to misuse.

API design should prioritize long-term maintainability over short-term convenience.

---

# API Philosophy

APIs should be:

* simple
* consistent
* explicit
* stable

An API should clearly communicate:

* what it does
* what it requires
* what it returns
* why it failed

---

# Design Before Implementation

Before creating an API:

Understand:

* who consumes it
* what problem it solves
* required data flow
* security requirements
* failure scenarios

Do not create endpoints before understanding usage.

---

# Existing API Rule

Existing API conventions have priority.

When working inside an existing project:

Follow existing:

* URL structure
* response format
* error patterns
* authentication approach
* naming conventions

Do not redesign APIs unnecessarily.

Consistency beats personal preference.

---

# Resource Naming

Prefer resource-based URLs.

Good:

GET /users

GET /users/{id}

POST /users

PATCH /users/{id}

Avoid action-based APIs when resource behavior is clear.

Bad:

GET /getUsers

POST /updateUser

Actions are acceptable when they represent actual operations.

Example:

POST /orders/{id}/cancel

---

# HTTP Methods

Use methods according to intent.

GET:

Retrieve data.

Must not modify state.

POST:

Create resources or execute operations.

PUT:

Replace complete resources.

PATCH:

Update partial resources.

DELETE:

Remove resources.

---

# Request Validation

Never trust incoming data.

Validate:

* required fields
* data types
* formats
* value ranges
* permissions

Invalid data should fail early.

---

# Response Design

Responses should be predictable.

Prefer consistent structures.

Example:

{
"data": {},
"message": "Success"
}

For collections:

{
"data": [],
"pagination": {}
}

Avoid changing response shapes unexpectedly.

---

# Error Responses

Errors should help clients understand failures.

Good errors include:

* clear message
* error type/code
* useful context

Example:

{
"error": "INVALID_EMAIL",
"message": "Email format is invalid"
}

Avoid exposing:

* stack traces
* database errors
* internal implementation details

---

# Status Codes

Use HTTP status codes correctly.

Common usage:

200 - Successful request

201 - Resource created

400 - Invalid request

401 - Authentication required

403 - Permission denied

404 - Resource not found

409 - Conflict

422 - Validation failure

500 - Unexpected server error

---

# Authentication

Authentication must be explicit.

Every protected endpoint should clearly define:

* who can access it
* required credentials
* token requirements

Never rely on hidden assumptions.

---

# Authorization

Authentication answers:

"Who are you?"

Authorization answers:

"What can you do?"

Always validate permissions server-side.

Never trust client-side restrictions.

---

# Pagination

Large collections must use pagination.

Avoid returning unlimited data.

Support:

* page size limits
* ordering
* filtering when needed

APIs should protect system resources.

---

# Filtering And Searching

Filtering should be:

* predictable
* documented
* validated

Avoid exposing raw database behavior through APIs.

Bad:

Directly converting all query parameters into database filters.

---

# Versioning

Do not version APIs unnecessarily.

Introduce versions when:

* breaking changes are required
* multiple clients need compatibility

Prefer backward-compatible evolution.

---

# Backward Compatibility

Avoid breaking consumers.

Prefer:

* adding optional fields
* supporting old behavior temporarily
* planned migrations

APIs are promises.

---

# External API Integration

When consuming external APIs:

Always handle:

* timeouts
* failures
* retries
* rate limits
* unexpected responses

External systems are unreliable.

Plan accordingly.

---

# Performance Considerations

Avoid:

* unnecessary database queries
* returning unused data
* large payloads
* inefficient serialization

Measure before optimizing.

---

# Security Rules

Never expose:

* secrets
* internal identifiers unnecessarily
* sensitive user data
* debug information

Always validate:

* input
* access
* ownership

---

# API Documentation

Document:

* purpose
* authentication
* parameters
* responses
* errors

Documentation describes contracts.

Not implementation.

---

# API Review Checklist

Before creating or modifying an API:

Ask:

1. Is this endpoint necessary?
2. Is the naming clear?
3. Is access protected?
4. Are inputs validated?
5. Are failures handled?
6. Can this evolve safely?

---

# Final Principle

A good API feels obvious.

Consumers should not need to understand your implementation to use your system correctly.