# Model Generator

Generate database models that protect data and represent the domain clearly.

Models should reflect reality.

Not convenience.

---

# Purpose

Guide creation of:

* database models
* schemas
* relationships
* migrations
* data structures

---

# Required References

Follow:

handbook/database/

examples/database-example.md

templates/framework-specific templates

---

# Generation Rule

Before creating models:

Understand:

* business domain
* relationships
* access patterns
* data lifecycle

Do not create tables blindly.

---

# Step 1: Identify Entity

Ask:

What real concept does this represent?

Examples:

User

Order

Invoice

Use meaningful names.

---

# Step 2: Define Responsibilities

Each model should have a clear purpose.

Avoid:

Generic models:

Data

Record

Info

without meaning.

---

# Step 3: Choose Fields

Add fields based on requirements.

For every field ask:

Why do we store this?

Unused data creates responsibility.

---

# Step 4: Select Data Types

Choose correct types.

Consider:

* validation
* storage
* querying
* future usage

---

# Step 5: Define Relationships

Understand:

How does this data connect?

Examples:

* one-to-one
* one-to-many
* many-to-many

---

# SQL Model Rules

Consider:

* constraints
* indexes
* normalization
* transactions

Use database capabilities.

---

# Document Database Rules

Design around:

* access patterns
* document ownership
* data grouping

Do not copy SQL design blindly.

---

# Step 6: Add Constraints

Protect data using:

* required fields
* uniqueness
* relationships

Invalid data should be difficult to create.

---

# Step 7: Add Indexes

Create indexes because:

queries need them

Not because:

field exists

---

# Step 8: Migration Planning

For existing systems:

Consider:

* current data
* compatibility
* rollback

---

# Step 9: Security Review

Identify sensitive fields.

Protect:

* credentials
* personal data
* private information

---

# Password Fields

Never store:

plain passwords

Use secure authentication patterns.

---

# Audit Fields

Add when useful:

created_at

updated_at

Do not add unnecessary tracking.

---

# Soft Delete

Use when requirements need:

* recovery
* history
* auditability

Not automatically.

---

# Validation

Combine:

application validation

*

database protection

---

# Performance Thinking

Consider:

How will this data be queried?

But avoid premature optimization.

---

# Existing Project Rule

Match:

* naming style
* ORM patterns
* migration process

Do not redesign existing schemas.

---

# AI Generation Rule

Claude must explain:

* model purpose
* relationships
* important decisions

---

# Avoid

Never automatically:

* add every possible field
* create unnecessary relations
* add indexes everywhere
* redesign database

---

# Output Format

Return:

## Model Purpose

What it represents.

## Structure

Fields and relationships.

## Reasoning

Important choices.

## Migration Notes

If applicable.

---

# Final Principle

Good models make invalid states difficult.

They protect the truth of the system.