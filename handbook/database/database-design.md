# Database Design

Databases store the long-term truth of a system.

Design them carefully.

Changing bad code is easy.

Changing bad data is expensive.

---

# Database Philosophy

A database should be:

* reliable
* understandable
* consistent
* maintainable

Design for correctness first.

Optimize with evidence.

---

# Existing Database Rule

Existing database design has priority.

Before changing:

Understand:

* schema history
* relationships
* production data
* migration impact

Never redesign databases casually.

---

# Data Ownership

Every table or collection should have clear ownership.

Ask:

"What real concept does this represent?"

Avoid creating storage without purpose.

---

# Naming

Names should explain meaning.

Good:

users

orders

payment_transactions

Bad:

data

details

info

Future developers should understand intent.

---

# Tables

Tables should represent entities or relationships.

Examples:

users

products

subscriptions

Avoid tables that mix unrelated concepts.

---

# Columns

Columns should store one clear piece of information.

Good:

first_name

last_name

Bad:

user_information

Structured data is easier to maintain.

---

# Data Types

Choose correct types.

Examples:

Dates should use date/time types.

Numbers should use numeric types.

JSON should not replace proper modeling.

---

# Primary Keys

Every table should have a reliable identifier.

Primary keys provide:

* identity
* relationships
* consistency

---

# Foreign Keys

Use relationships when data depends on other data.

Foreign keys protect integrity.

Do not rely only on application logic.

---

# Constraints

Databases should enforce important rules.

Examples:

* uniqueness
* required fields
* valid relationships

Bad data should be impossible.

---

# Normalization

Normalize data to reduce:

* duplication
* inconsistency
* update problems

Start with clean structure.

---

# Denormalization

Denormalization is acceptable for:

* performance
* reporting
* scaling requirements

Do it intentionally.

Not by default.

---

# JSON Columns

JSON fields are useful for:

* flexible metadata
* external payloads
* changing structures

Avoid using JSON to escape database design.

---

# Audit Fields

Important records should consider:

created_at

updated_at

Additional audit fields depend on requirements.

---

# Soft Deletes

Use soft deletes only when needed.

Consider:

* recovery requirements
* compliance
* historical tracking

Do not add automatically.

---

# Status Fields

Avoid unclear statuses.

Bad:

status = "done"

Prefer defined states.

Example:

OrderStatus:

PENDING

PAID

SHIPPED

---

# Relationships

Design relationships based on real rules.

Understand:

* one-to-one
* one-to-many
* many-to-many

Do not guess.

---

# Large Tables

Consider growth.

Large tables require:

* indexing strategy
* query planning
* maintenance

Think beyond development data.

---

# Security

Never store sensitive data casually.

Protect:

* passwords
* tokens
* personal information

Use proper security practices.

---

# Schema Changes

Production schema changes require:

* migrations
* testing
* rollback consideration

Data changes are serious.

---

# Performance

Do not optimize blindly.

Measure:

* queries
* load
* bottlenecks

Then improve.

---

# Documentation

Document unusual decisions.

Explain why something exists.

Future maintainers need context.

---

# Warning Signs

Review database design when:

* everything is stored as JSON
* relationships exist only in code
* duplicate data constantly conflicts
* nobody understands table purpose

---

# Database Checklist

Before creating structures:

[ ] Entity purpose is clear

[ ] Relationships are correct

[ ] Constraints protect data

[ ] Types are appropriate

[ ] Future changes considered

---

# Final Principle

Applications change often.

Data survives for years.

Design databases with respect.