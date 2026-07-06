# Database Indexing

Indexes improve data lookup performance.

They are optimization tools.

They are not free.

---

# Indexing Philosophy

Indexes should exist because queries need them.

Not because columns exist.

Measure first.

Optimize intentionally.

---

# Existing Database Rule

Existing indexing strategy has priority.

Before changing:

Understand:

* current indexes
* query patterns
* database workload
* production behavior

Do not add or remove indexes blindly.

---

# What Indexes Do

Indexes help databases find data faster.

They improve:

* filtering
* searching
* sorting
* joins

when designed correctly.

---

# Index Cost

Every index has a cost.

Indexes affect:

* storage usage
* insert speed
* update speed
* maintenance

More indexes are not always better.

---

# When To Add Indexes

Consider indexes for:

* frequent WHERE conditions
* JOIN fields
* sorting fields
* lookup columns

Based on real queries.

---

# Do Not Index Everything

Bad:

Adding indexes to every column.

Problems:

* slower writes
* wasted storage
* unnecessary complexity

---

# Primary Keys

Primary keys are indexed automatically in most databases.

Understand what already exists.

Avoid duplicate indexes.

---

# Foreign Keys

Foreign key columns often benefit from indexes.

Especially when:

* joining frequently
* filtering relationships

Verify database behavior.

---

# Unique Indexes

Use uniqueness when data requires it.

Examples:

email

username

Protect correctness.

Not only performance.

---

# Composite Indexes

Use composite indexes for queries involving multiple columns.

Example:

WHERE user_id = ?

AND status = ?

Index:

(user_id, status)

---

# Column Order Matters

Composite index order affects usage.

Design based on:

* filtering
* sorting
* query patterns

---

# Low Cardinality Columns

Be careful indexing fields like:

status

boolean flags

They may not provide much benefit alone.

---

# Query Analysis

Before adding indexes:

Check:

* execution plan
* query time
* scanned rows

Understand the problem.

---

# Index For Reads vs Writes

Read-heavy systems may benefit from more indexes.

Write-heavy systems require caution.

Balance workload.

---

# Unused Indexes

Remove indexes that:

* are unused
* duplicate others
* increase cost

Indexes need maintenance.

---

# Search Requirements

Search may need specialized solutions.

Examples:

* full text indexes
* search engines
* trigram indexes

Choose based on requirements.

---

# Large Tables

Index changes on large tables require planning.

Consider:

* locks
* migration time
* production impact

---

# ORM Indexing

ORM configuration does not remove database knowledge.

Understand generated indexes.

Review migrations.

---

# Performance Problems

Do not guess.

Bad:

API slow

↓

Add random indexes

Good:

Measure

↓

Find slow query

↓

Optimize

---

# Documentation

Document unusual indexes.

Explain why they exist.

Future developers should not remove important indexes.

---

# Warning Signs

Review indexes when:

* every column is indexed
* slow queries are fixed by guessing
* nobody knows why indexes exist
* writes become unexpectedly slow

---

# Index Checklist

Before adding:

[ ] Query requires it

[ ] Usage measured

[ ] Existing indexes checked

[ ] Write impact considered

[ ] Production impact reviewed

---

# Final Principle

Indexes are tools.

Good indexing solves measured problems.

Bad indexing creates new ones.