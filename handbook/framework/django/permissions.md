# Django Permissions

Permissions control what authenticated users are allowed to do.

Authentication verifies identity.

Permissions protect actions and resources.

---

# Permission Philosophy

Permissions answer:

"Can this user perform this action?"

They should be:

* explicit
* secure
* consistent
* easy to understand

Never assume access.

---

# Existing Project Rule

Existing permission systems have priority.

Before changing:

Understand:

* authentication model
* roles
* custom permissions
* ownership rules

Do not replace permission architecture unnecessarily.

---

# Authentication vs Permission

Authentication:

Who is the user?

Permission:

What can this user do?

Keep responsibilities separate.

---

# DRF Permission Location

Standard:

apps/

└── users/

```
├── permissions.py
```

or shared:

permissions/

when reused.

---

# Default Security Rule

Deny by default.

Grant access intentionally.

Avoid accidentally exposing resources.

---

# Permission Classes

Use DRF permission classes.

Example:

permission_classes = [
IsAuthenticated
]

Access requirements should be visible.

---

# IsAuthenticated Is Not Enough

Common mistake:

User is logged in.

Therefore user can access everything.

Wrong.

Always check ownership and permissions.

---

# Object Permissions

Protect individual resources.

Example:

A user can access:

their own order.

Not:

every order.

---

# Ownership Checks

Always verify ownership.

Example:

User requests:

/orders/123

Check:

Does this order belong to the user?

---

# Custom Permissions

Create custom permissions when rules repeat.

Example:

IsOrderOwner

IsAdminUser

CanApproveInvoice

Names should explain access rules.

---

# Role Based Permissions

Roles group access.

Examples:

Admin

Manager

Customer

Avoid scattering role checks everywhere.

---

# Permission Based Access

For complex systems prefer action permissions.

Example:

invoice.create

invoice.approve

invoice.delete

Actions are clearer.

---

# Business Permissions

Some permissions depend on state.

Example:

Order can be cancelled only before shipping.

This is business authorization.

Handle explicitly.

---

# Views And Permissions

Views declare access requirements.

Complex decisions may call:

* services
* permission helpers

Keep rules understandable.

---

# Serializer Security

Do not depend on serializers alone.

Hiding fields is not authorization.

Always protect access before data exposure.

---

# Queryset Security

Filter data properly.

Good:

User sees only owned records.

Avoid:

returning everything and hiding later.

---

# Admin Access

Protect admin operations carefully.

Admin permissions should still be intentional.

Avoid unlimited assumptions.

---

# Temporary Bypasses

Avoid:

temporary admin access

debug permissions

permission disabling

Temporary security shortcuts become permanent.

---

# Error Responses

Avoid leaking information.

Good:

Permission denied.

Avoid:

This private object exists but you cannot access it.

---

# Testing Permissions

Test:

* allowed access
* denied access
* ownership
* role boundaries

Security requires negative tests.

---

# Warning Signs

Review permissions when:

* only IsAuthenticated exists everywhere
* users can access others' data
* role checks are duplicated
* permissions are unclear

---

# Permission Checklist

Before completion:

[ ] Authentication verified

[ ] Permission verified

[ ] Ownership checked

[ ] Default access restricted

[ ] Sensitive data protected

[ ] Negative tests exist

---

# Final Principle

Login proves identity.

Permissions prove access.

Every protected action requires both.