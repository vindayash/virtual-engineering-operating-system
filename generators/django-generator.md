# Django Generator

Generate Django applications using Django conventions.

Use the framework.

Do not recreate another architecture inside it.

---

# Purpose

Guide generation of:

* Django projects
* Django apps
* DRF APIs
* application modules

using maintainable patterns.

---

# Required References

Follow:

templates/django-template.md

handbook/framework/

handbook/backend/

handbook/security/

---

# Generation Rule

Before creating files:

Understand:

* application purpose
* domain structure
* API requirements
* database needs

Generate intentionally.

---

# Step 1: Determine Structure

Small project:

Use:

* default Django structure

Growing project:

Use:

apps/

Large project:

Separate domains clearly.

Avoid unnecessary folders.

---

# Step 2: Create Apps

Create apps around business domains.

Good:

users

orders

billing

Avoid:

helpers

logic

misc

---

# Step 3: Generate Models

Models contain:

* fields
* relationships
* constraints
* model-specific behavior

Keep models meaningful.

---

# Step 4: Generate Serializers

For DRF create serializers for:

* input validation
* output representation

Do not expose unnecessary fields.

---

# Step 5: Generate Views

Generate:

* APIViews
* ViewSets
* Generic Views

based on project style.

Follow existing patterns.

---

# Step 6: Generate URLs

Create predictable routes.

Keep routing organized.

---

# Step 7: Generate Permissions

For protected resources:

Create permission classes.

Check:

* authentication
* authorization
* ownership

---

# Step 8: Generate Managers

Managers are optional.

Use for:

* reusable queries
* model-specific database logic

Do not create empty managers.

---

# Step 9: Generate Services

Services are optional.

Generate for:

* workflows
* external integrations
* multiple model operations

---

# Avoid Empty Services

Do not generate:

View

↓

Service

↓

Model.objects.create()

without business logic.

---

# Step 10: Generate Settings

Separate:

* development
* production

Use environment configuration.

Never hardcode secrets.

---

# Step 11: Generate Admin

Add admin configuration when useful.

Avoid unnecessary customization.

---

# Step 12: Generate Tests

Prioritize:

* business rules
* API behavior
* permissions
* important workflows

---

# Signal Generation

Generate signals carefully.

Use for:

independent reactions

Avoid:

hidden business processes

---

# Database Rules

Generate migrations carefully.

Consider existing data.

---

# Security Rules

Follow:

handbook/security/

Include:

* validation
* permissions
* safe responses

---

# Dependency Rules

Before installing packages:

Check Django built-in capabilities.

---

# Existing Project Rule

Existing structure wins.

Do not reorganize projects automatically.

---

# AI Generation Rule

Claude must generate:

* project-consistent files
* minimal needed structure
* framework-friendly code

---

# Never Generate Automatically

Avoid:

* repository pattern everywhere
* unnecessary service layers
* custom auth systems
* replacing Django features

---

# Output Format

Return:

## Structure

Files generated.

## Reasoning

Why this approach.

## Implementation

Code changes.

## Notes

Important decisions.

---

# Final Principle

Generate Django code that Django developers expect.

Simple.

Explicit.

Maintainable.