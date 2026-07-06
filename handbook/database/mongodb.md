# MongoDB Standards

MongoDB stores data as documents.

Use document design intentionally.

MongoDB is not relational SQL with JSON syntax.

---

# MongoDB Philosophy

MongoDB should be designed around:

* application access patterns
* document ownership
* query requirements

Design documents based on usage.

Not only entities.

---

# Existing Database Rule

Existing MongoDB design has priority.

Before changing:

Understand:

* collections
* document structure
* indexes
* query patterns
* data volume

Do not remodel existing databases unnecessarily.

---

# Collections

Collections should represent meaningful data groups.

Good:

users

orders

events

Avoid:

data

objects

records

Names should communicate purpose.

---

# Document Design

A document should contain data that naturally belongs together.

Think:

"What data is usually accessed together?"

---

# Embedding Documents

Embedding works well for:

* owned data
* small related data
* data accessed together

Example:

Order

contains

order items

---

# Referencing Documents

Use references when:

* data grows independently
* duplication creates problems
* relationships are large

Example:

Many orders reference users.

---

# Avoid SQL Modeling

Do not automatically create:

one collection per relational table.

MongoDB requires document thinking.

---

# Avoid Giant Documents

Documents have limits.

Avoid:

* endlessly growing arrays
* huge nested structures
* unrelated information

Large documents become problems.

---

# Schema Flexibility

Flexible schema does not mean no schema.

Applications still need:

* consistency
* validation
* expected structures

---

# Required Fields

Define required data clearly.

Avoid unpredictable documents.

Example:

Some users have email.

Some users have contact.email.

creates complexity.

---

# Indexing

Create indexes based on queries.

Common:

* lookup fields
* filters
* sorting fields

Do not index everything.

---

# Compound Indexes

Use compound indexes for common query patterns.

Example:

user_id

*

created_at

when queried together.

---

# Aggregation Pipelines

Aggregation is powerful.

Use for:

* transformations
* analytics
* grouped calculations

Keep pipelines understandable.

---

# Large Aggregations

For large datasets:

Consider:

* indexes
* memory usage
* execution time

Aggregation design matters.

---

# Pagination

Avoid loading unlimited documents.

Use:

* limits
* cursors
* efficient pagination

Large collections require planning.

---

# Updates

Be intentional.

Prefer targeted updates.

Avoid replacing entire documents unnecessarily.

---

# Atomic Operations

Use MongoDB atomic updates when needed.

Examples:

increment counters

update specific fields

Avoid unsafe read-modify-write patterns.

---

# Transactions

MongoDB supports transactions.

Use when multiple document changes require consistency.

Do not use transactions unnecessarily.

---

# Data Duplication

Duplication can be acceptable.

MongoDB often trades duplication for performance.

Keep duplicated data controlled.

---

# Validation

Validate:

* application input
* document structure
* important fields

Do not rely on flexibility alone.

---

# Object IDs

Use identifiers consistently.

Avoid mixing:

strings

ObjectIds

without reason.

---

# Performance

Before optimization:

Measure.

Check:

* slow queries
* indexes
* execution plans

Do not guess.

---

# Security

Protect:

* connection strings
* credentials
* sensitive fields

Never expose database access.

---

# Backups

Production databases need:

* backup strategy
* restore testing

Storage failure happens.

---

# Warning Signs

Review MongoDB usage when:

* every document looks like SQL rows
* everything is stored in one collection
* indexes are random
* document structures constantly change

---

# MongoDB Checklist

Before completion:

[ ] Access patterns understood

[ ] Embedding/reference decision made

[ ] Indexes match queries

[ ] Documents remain manageable

[ ] Data consistency considered

---

# Final Principle

MongoDB flexibility is power.

Use it to model data better.

Not to avoid designing data.