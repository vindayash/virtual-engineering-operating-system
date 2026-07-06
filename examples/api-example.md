# API Example

Reference examples for designing maintainable APIs.

APIs are contracts.

Make them predictable.

---

# Goal

Create APIs that are:

* consistent
* secure
* understandable
* easy to consume

---

# Resource Naming

Good:

GET /api/v1/users

Meaning:

Retrieve users.

---

Bad:

GET /api/v1/getAllUsers

Problem:

Action-based naming creates inconsistency.

---

# Single Resource

Good:

GET /api/v1/users/{user_id}

Meaning:

Retrieve one user resource.

---

Bad:

POST /api/v1/user/details/get

Problem:

Unclear responsibility.

---

# HTTP Method Usage

GET:

Retrieve data.

POST:

Create resource or perform action.

PUT/PATCH:

Modify resource.

DELETE:

Remove resource.

---

# API Versioning

Good:

/api/v1/orders

Benefits:

* supports compatibility
* allows future changes

---

# Request Validation Example

Good:

Validate:

* required fields
* types
* allowed values

Reject invalid input early.

---

Bad:

Accept request.

Process everything.

Fail somewhere later.

---

# Response Example

Good:

Return only needed fields.

Example:

User response:

id

name

email

---

Bad:

Return complete database object.

Problems:

* exposes internals
* leaks data
* couples API to database

---

# Error Example

Good:

{
"message": "User not found"
}

Safe.

Clear.

---

Bad:

{
"error": "users_table query failed line 82"
}

Leaks internals.

---

# Authentication Example

Protected endpoint:

Verify identity first.

Question:

Who is making this request?

---

# Authorization Example

After authentication:

Verify access.

Question:

Can this user access this resource?

---

# Ownership Example

Request:

GET /orders/100

Check:

Does this order belong to the user?

---

# Pagination Example

Good:

GET /users?page=1&limit=20

Avoid:

return every record

---

# Filtering Example

Good:

GET /orders?status=pending

Validate filters before querying.

---

# Large Response Example

Avoid:

Huge payloads.

Prefer:

* pagination
* selected fields
* optimized responses

---

# File Upload Example

Validate:

* size
* type
* permissions

Never trust uploaded files.

---

# API Documentation Example

Document:

* purpose
* request
* response
* errors

Avoid documenting obvious implementation.

---

# Breaking Change Example

Bad:

Remove response field suddenly.

Good:

Create new API version or migration plan.

---

# Security Checklist Example

Before exposing endpoint:

[ ] Authentication checked

[ ] Authorization checked

[ ] Input validated

[ ] Response controlled

[ ] Errors safe

---

# Final Principle

The best APIs are boring.

They behave exactly how developers expect.