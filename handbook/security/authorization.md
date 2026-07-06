# Authorization Security

Authorization decides what an authenticated identity can access.

Authentication proves identity.

Authorization protects resources.

---

# Authorization Philosophy

Every protected action should answer:

"Is this identity allowed to do this?"

Never assume permission.

---

# Existing System Rule

Existing authorization models have priority.

Before changing:

Understand:

* roles
* permissions
* ownership rules
* access policies

Do not replace authorization systems unnecessarily.

---

# Authentication Is Not Authorization

A common mistake:

User logged in

=

User allowed

This is incorrect.

Always verify access.

---

# Deny By Default

Default behavior should be:

No access

Then explicitly allow required actions.

---

# Least Privilege

Give only required permissions.

Avoid:

* unnecessary admin access
* global permissions
* unlimited access

Access should match responsibility.

---

# Resource Ownership

Always check ownership.

Example:

User requests:

/orders/123

Verify:

Does this user own order 123?

---

# Prevent IDOR

Insecure Direct Object Reference happens when:

User changes ID

and accesses another user's data.

Example:

/users/100

changed to:

/users/101

Always verify authorization.

---

# Role Based Access Control

RBAC groups permissions by roles.

Examples:

Admin

Manager

Customer

Roles should have clear meaning.

---

# Permission Based Access

For complex systems use specific permissions.

Examples:

invoice.create

invoice.approve

invoice.delete

Actions become explicit.

---

# Avoid Hardcoded Permissions

Avoid scattering:

if user.role == "admin"

everywhere.

Centralize permission logic.

---

# Object Level Permissions

Check access at resource level.

Examples:

* files
* projects
* orders
* accounts

Not only endpoint level.

---

# Administrative Access

Admin users still require controls.

Avoid assuming:

Admin can do everything everywhere.

Critical actions may need extra protection.

---

# Multi Tenant Security

For multi tenant systems:

Always isolate:

* organizations
* customers
* workspaces

Tenant boundaries are security boundaries.

---

# Database Queries

Filter by permission early.

Good:

Fetch only allowed records.

Bad:

Fetch everything.

Filter later.

---

# API Authorization

Every protected endpoint needs access rules.

Examples:

GET

POST

PUT

DELETE

Each action may require different permissions.

---

# Background Jobs

Background processing also requires authorization thinking.

Ensure jobs cannot process unauthorized data.

---

# Internal Services

Internal APIs still require protection.

Network location alone is not security.

---

# Permission Changes

Permission updates should be controlled.

Track important changes when needed.

---

# Error Responses

Avoid leaking private resource existence.

Example:

Do not reveal sensitive objects through error details.

---

# Testing Authorization

Always test:

Allowed user

Denied user

Security requires negative tests.

---

# Common Tests

Verify:

* users cannot access others' data
* roles have correct limits
* removed permissions stop access

---

# Warning Signs

Review authorization when:

* only login checks exist
* IDs directly expose data
* everyone becomes admin
* permission checks are duplicated

---

# Authorization Checklist

Before completion:

[ ] Identity verified

[ ] Permission checked

[ ] Ownership validated

[ ] Default access restricted

[ ] Negative tests included

---

# Final Principle

Authentication opens the door.

Authorization decides which rooms you can enter.