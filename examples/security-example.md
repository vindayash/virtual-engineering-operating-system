# Security Example

Reference examples for secure engineering decisions.

Security should be practical.

Security should be consistent.

---

# Goal

Create systems that protect:

* users
* data
* infrastructure
* business logic

---

# Authentication Example

Question:

Who is this user?

---

Good:

Verify identity using trusted authentication flow.

---

Bad:

Trust user information sent from frontend.

Problem:

Clients can be modified.

---

# Authorization Example

Question:

Can this user perform this action?

---

Bad:

User is logged in.

Allow access.

---

Good:

User is logged in.

Check permission.

Check ownership.

Allow access.

---

# Ownership Example

Request:

GET /api/orders/500

Check:

Does authenticated user have access to order 500?

---

# IDOR Example

Bad:

User changes:

/users/1

to:

/users/2

and receives another user's data.

---

Good:

Always verify ownership.

---

# Password Example

Bad:

Store:

password123

directly in database.

---

Good:

Store securely hashed password.

---

# Secret Example

Bad:

API_KEY = "real-secret-value"

inside source code.

---

Good:

API_KEY loaded from secure configuration.

---

# Environment Example

Good:

.env.example

Contains:

API_KEY=

No real values.

---

# Logging Example

Bad:

Log complete request:

including passwords and tokens.

---

Good:

Log useful debugging information without secrets.

---

# API Response Example

Bad:

Return full database record.

Problem:

May expose internal fields.

---

Good:

Return explicit response schema.

---

# Error Example

Bad:

Database connection failed with password xyz

---

Good:

Internal server error

Log details safely internally.

---

# Input Example

Bad:

Trust incoming request data.

---

Good:

Validate:

* type
* format
* permissions

before processing.

---

# File Upload Example

Bad:

Accept any uploaded file.

---

Good:

Validate:

* file size
* file type
* access rules

---

# Dependency Example

Bad:

Install package without checking.

---

Good:

Review:

* purpose
* maintenance
* security

---

# Token Example

Bad:

Tokens never expire.

---

Good:

Use:

* expiration
* validation
* revocation strategy when needed

---

# Admin Example

Bad:

Admin bypasses every security rule.

---

Good:

Admin actions still have controlled access.

---

# Security Fix Example

Bad:

Rewrite entire authentication system immediately.

---

Good:

Understand issue.

Apply targeted safe fix.

---

# Final Checklist Example

Before release:

[ ] Authentication works

[ ] Authorization checked

[ ] Secrets protected

[ ] Inputs validated

[ ] Sensitive data hidden

---

# Final Principle

Good security prevents mistakes.

It does not depend on everyone being perfect.