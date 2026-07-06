# Database Example

Reference examples for designing and changing databases.

Protect correctness first.

Optimize with understanding.

---

# Goal

Create databases that are:

* reliable
* understandable
* efficient
* maintainable

---

# Database Selection Example

Choose based on data.

Not popularity.

---

# SQL Good Fit Example

Data:

Users

Orders

Payments

Characteristics:

* relationships
* transactions
* consistency required

Good choice:

Relational database

---

# Document Database Good Fit Example

Data:

Flexible documents

Changing structure

Nested information

Good choice:

Document database

---

# Bad Selection Example

Choosing technology because:

"Large companies use it."

Problem:

Their problems may not be your problems.

---

# Schema Design Example

Good:

User

Order

Product

Clear ownership.

---

Bad:

Data

Info

Details

Unclear meaning.

---

# Relationship Example

Think:

How does data connect?

How will queries access it?

Design from usage.

---

# Index Example

Good:

Query frequently searches:

email

Add index because access pattern exists.

---

Bad:

Add indexes to every column.

Problems:

* storage increase
* slower writes
* unnecessary complexity

---

# Query Example

Bad:

For every user:

Fetch orders separately.

Problem:

Repeated database calls.

---

Good:

Fetch required data efficiently.

Understand ORM behavior.

---

# Migration Example

Good:

1. Add new field

2. Deploy compatible code

3. Move data

4. Remove old field later

---

Bad:

Remove field immediately.

Break running systems.

---

# Transaction Example

Payment workflow:

Create payment

Update order

Reduce balance

Should succeed together.

Use transaction.

---

# Large Data Example

Bad:

Load 10 million records into memory.

Good:

Use:

* batching
* pagination
* streaming

---

# Data Validation Example

Protect data using:

Application validation

*

Database constraints

---

# Production Change Example

Before changing:

Ask:

How much data exists?

Can this fail?

How do we recover?

---

# Backup Example

Risky changes require recovery planning.

Data loss is harder than code failure.

---

# Cache Example

Bad:

Database slow.

Immediately add cache.

---

Good:

Analyze query.

Optimize.

Then cache if needed.

---

# Security Example

Avoid storing:

* plain passwords
* secrets
* unnecessary sensitive data

---

# Permission Example

Application user should have required database permissions.

Not unlimited admin access.

---

# Final Principle

Applications can be rewritten.

Data must be protected.