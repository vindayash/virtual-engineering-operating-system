# Django Apps

Django apps organize related functionality.

Apps should represent meaningful responsibilities.

Not random folders.

---

# App Philosophy

A Django app should answer:

"What responsibility does this part of the system own?"

Apps create boundaries.

They should improve understanding.

---

# Existing Project Rule

Existing app organization has priority.

Before creating or moving apps:

Understand:

* current domains
* dependencies
* naming patterns
* team conventions

Do not reorganize apps unnecessarily.

---

# When To Create An App

Create a new app when there is a clear domain.

Good:

users

orders

payments

notifications

Each owns a responsibility.

---

# When Not To Create An App

Avoid creating apps for:

* every database table
* every small feature
* imaginary future separation

More apps do not automatically improve architecture.

---

# Avoid Giant Apps

Avoid:

core/

containing:

* users
* payments
* reports
* notifications

Large mixed apps lose ownership.

---

# Avoid Tiny Apps

Avoid:

user_email/

user_profile/

user_settings/

when they always change together.

Related behavior can live together.

---

# App Ownership

Each app should own:

* models
* views
* serializers
* permissions
* tests

for its domain.

Ownership should be obvious.

---

# App Communication

Apps can communicate.

Keep communication:

* explicit
* understandable
* minimal

Avoid circular dependencies.

---

# Cross App Logic

When workflows involve multiple apps:

Use services when helpful.

Example:

Order checkout:

* orders
* payments
* inventory

A workflow service can coordinate.

---

# Models Across Apps

Relationships between apps are normal.

Example:

Order references User.

Avoid creating unnecessary separation just to avoid relationships.

---

# Shared Functionality

Shared code must have clear purpose.

Avoid:

common/

becoming a dumping ground.

Better:

notifications/

files/

audit/

when responsibility exists.

---

# Core App Usage

Only create core apps when they have meaning.

Acceptable:

core configuration utilities

base models

shared framework behavior

Avoid placing all business logic in core.

---

# App Names

Names should represent domains.

Good:

billing

inventory

analytics

Bad:

manager

handler

misc

---

# Reusable Apps

Build reusable apps only when reuse exists.

Do not design every app as a public package.

Most apps belong to one project.

---

# Services Inside Apps

Services are optional.

Use:

services.py

when workflows grow.

Avoid empty service layers.

---

# Selectors Inside Apps

Selectors are optional.

Useful for:

* complex queries
* repeated reads
* optimized fetching

Do not wrap simple ORM calls.

---

# App Migration

Changing app boundaries is expensive.

Before splitting apps:

Confirm:

* responsibility problems exist
* complexity requires it
* benefits justify migration

---

# Testing Apps

Tests should verify:

* app behavior
* business rules
* permissions
* important workflows

Follow app ownership.

---

# Warning Signs

Review apps when:

* nobody knows where code belongs
* apps depend on everything
* circular imports appear
* every feature creates a new app
* one app owns the entire system

---

# App Checklist

Before creating an app:

[ ] Does it represent a domain?

[ ] Does ownership exist?

[ ] Will it reduce complexity?

[ ] Is existing structure respected?

[ ] Is this not premature separation?

---

# Final Principle

A Django app is a responsibility boundary.

Create apps because the system needs ownership.

Not because the folder list looks cleaner.