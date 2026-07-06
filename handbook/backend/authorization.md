# Authorization

Authorization controls what an authenticated identity is allowed to do.

It answers one question:

"What actions are permitted?"

Authentication proves identity.

Authorization protects resources.

---

# Authorization Philosophy

Every protected action requires permission.

A secure system should:

* verify access explicitly
* protect resources by default
* deny unsafe actions
* avoid hidden trust

Never assume access.

---

# Authentication vs Authorization

Authentication:

"Who is this user?"

Authorization:

"Can this user perform this action?"

A valid identity does not automatically mean permission.

---

# Existing Project Rule

Existing authorization patterns have priority.

Before changing permissions:

Understand:

* current access model
* roles
* ownership rules
* business requirements

Do not introduce a new permission system unnecessarily.

---

# Deny By Default

Default behavior should be:

No access.

Grant permissions intentionally.

Systems should fail closed.

Not fail open.

---

# Server Side Enforcement

Authorization must happen on the backend.

Never trust:

* frontend restrictions
* hidden fields
* disabled buttons
* client-side roles

Clients can be modified.

---

# Resource Ownership

Always verify ownership.

Example:

A user requesting:

GET /orders/123

must have permission for order 123.

Not just be logged in.

---

# Role Based Access

Roles represent groups of permissions.

Example:

Admin

Manager

User

Avoid:

hardcoding role checks everywhere.

Keep access rules understandable.

---

# Permission Based Access

For complex systems:

Prefer permissions describing actions.

Examples:

invoice.create

invoice.approve

user.delete

Actions are clearer than vague roles.

---

# Least Privilege Principle

Give users and services only the access they need.

Avoid:

* unnecessary admin access
* overly broad permissions
* permanent elevated access

More access creates more risk.

---

# Business Rules And Permissions

Some authorization depends on business state.

Example:

A user can cancel an order only before shipment.

This is business authorization.

Handle it explicitly.

---

# Administrative Access

Admin functionality requires extra care.

Protect:

* user management
* configuration changes
* sensitive operations

Admin does not mean unlimited without control.

---

# Service Authorization

Internal services also require access control.

Protect:

* APIs
* queues
* cloud resources
* databases

Internal systems can still be compromised.

---

# Database Level Protection

When needed:

Use:

* constraints
* policies
* limited credentials

Do not rely only on application assumptions.

---

# Authorization Failures

Return safe errors.

Avoid exposing:

* whether private resources exist
* internal permission logic

Example:

"Access denied"

instead of:

"User exists but you are not the owner"

---

# Logging Access Events

Log important security events:

* permission failures
* privilege changes
* sensitive actions

Never log sensitive data unnecessarily.

---

# Avoid Permission Duplication

Access rules scattered everywhere become dangerous.

Prefer:

* reusable checks
* clear ownership
* consistent enforcement

Avoid hidden permission logic.

---

# Testing Authorization

Test:

* allowed users
* denied users
* ownership boundaries
* privilege escalation attempts

Authorization bugs become security bugs.

---

# Common Mistakes

Avoid:

* checking only login status
* trusting request data
* exposing all records
* forgetting ownership checks
* adding temporary admin bypasses

Temporary security shortcuts become permanent.

---

# Authorization Review Checklist

Before completing:

[ ] User identity verified

[ ] Permission checked

[ ] Ownership validated

[ ] Default access is restricted

[ ] Client data is not trusted

[ ] Tests cover denied access

---

# Final Principle

Authentication opens the door.

Authorization decides which rooms can be entered.

Every action must prove permission.