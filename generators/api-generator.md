# API Generator

Generate APIs that are predictable, secure and maintainable.

APIs are long-term contracts.

Design carefully.

---

# Purpose

Guide creation of:

* endpoints
* request schemas
* responses
* validation
* API modules

---

# Required References

Follow:

templates/

examples/api-example.md

handbook/backend/

handbook/security/

---

# Generation Rule

Before creating an API:

Understand:

* resource being exposed
* user actions
* permissions
* data requirements

---

# Step 1: Define Resource

Start with:

What object or action does this represent?

Examples:

User

Order

Payment

---

# Step 2: Choose Endpoint Design

Prefer resource style.

Good:

GET /users/{id}

Avoid:

GET /getUserById

---

# Step 3: Choose HTTP Methods

Use:

GET:

Retrieve.

POST:

Create or execute action.

PUT/PATCH:

Modify.

DELETE:

Remove.

---

# Step 4: Add Versioning

Use when API compatibility matters.

Example:

/api/v1/

Do not break existing clients.

---

# Step 5: Generate Request Schema

Validate:

* required fields
* data types
* formats
* limits

Never trust input.

---

# Step 6: Generate Response Schema

Return:

only required data

Avoid exposing:

database models directly

---

# Step 7: Add Authentication

Ask:

Who is making this request?

Add authentication when needed.

---

# Step 8: Add Authorization

Ask:

Can this identity perform this action?

Check:

* roles
* permissions
* ownership

---

# Step 9: Add Business Logic

Place logic based on complexity.

Simple:

handler/view

Complex:

service

Avoid unnecessary layers.

---

# Step 10: Add Database Access

Use project pattern:

* ORM
* CRUD
* managers
* repositories if already used

Follow existing style.

---

# Step 11: Add Error Handling

Create predictable errors.

Use:

* custom exceptions when helpful
* safe messages
* correct status codes

---

# Step 12: Add Documentation

Generate:

* descriptions
* examples
* API metadata

when useful.

---

# Step 13: Add Tests

Prioritize:

* successful requests
* validation errors
* permission failures

---

# Security Checklist

Generated APIs must check:

[ ] Input validation

[ ] Authentication

[ ] Authorization

[ ] Safe responses

[ ] Safe errors

---

# Existing API Rule

For existing projects:

Match:

* naming
* response format
* error format
* structure

Consistency wins.

---

# AI Generation Rule

Claude must not:

* expose internal models
* skip permission checks
* create unnecessary abstractions

---

# Avoid

Never generate:

* unlimited responses
* unsafe endpoints
* hidden security assumptions
* unrelated changes

---

# Output Format

Return:

## API Contract

Endpoint design.

## Files

Generated changes.

## Implementation

Code.

## Security Notes

Important checks.

---

# Final Principle

A good API feels obvious.

Users should not need to guess.