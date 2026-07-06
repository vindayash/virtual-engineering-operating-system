# Architecture Decision Examples

Examples help understand good architecture decision records.

The goal is not only recording choices.

The goal is preserving reasoning.

---

# Example Philosophy

Good architecture decisions explain:

Why this solution?

Why not alternatives?

What tradeoffs exist?

Future engineers should understand the context.

---

# Good ADR Example

# Title

Use PostgreSQL As Primary Database

---

# Status

Accepted

---

# Context

The application requires:

* structured data
* relationships between entities
* transactions
* reporting queries

Data consistency is important.

---

# Decision

Use PostgreSQL as the primary database.

---

# Alternatives Considered

MongoDB:

Rejected because relationships and transactions are core requirements.

MySQL:

Valid option but PostgreSQL provides required features and existing team experience.

---

# Consequences

Positive:

* strong consistency
* relational modeling
* mature ecosystem

Negative:

* schema changes require migrations
* horizontal scaling requires planning

---

# Why This Is Good

Decision is based on:

* requirements
* constraints
* tradeoffs

Not popularity.

---

# Bad ADR Example

# Title

Use Microservices

---

# Decision

Use microservices because they scale better.

---

# Problem

Missing.

---

# Alternatives

Missing.

---

# Tradeoffs

Missing.

---

# Why This Is Bad

It chooses technology before understanding requirements.

---

# Example: Adding Redis

Good reasoning:

Problem:

Database queries for repeated dashboard data are slow.

Measured:

Same expensive aggregation runs thousands of times.

Decision:

Cache calculated dashboard results using Redis.

Tradeoff:

Must handle cache invalidation.

---

# Bad Redis Decision

"We should add Redis because large applications use Redis."

Problem unknown.

Need unknown.

Benefit unknown.

---

# Example: Adding Service Layer

Good:

Current workflow:

* validates order
* updates inventory
* processes payment
* sends notification

Decision:

Move workflow into OrderService.

Reason:

View contains multiple responsibilities.

---

# Bad Service Layer Decision

"Every project must have services."

Result:

View

↓

Service

↓

One model call

No value added.

---

# Example: Docker Adoption

Good:

Problem:

Different developer environments create setup issues.

Decision:

Use Docker Compose for local consistency.

Tradeoff:

Developers need Docker knowledge.

---

# Bad Docker Adoption

"Everything should use Docker."

No actual problem identified.

---

# Example: Refactoring Legacy Code

Good:

Problem:

Payment calculation duplicated in five locations.

Decision:

Extract shared calculation module.

Benefit:

Single source of truth.

---

# Bad Refactor

"This code does not look modern.

Rewrite everything."

Risk ignored.

---

# Example: Database Change

Good:

Problem:

Users require multiple addresses.

Decision:

Create separate address table.

Reason:

Relationship can grow independently.

---

# Bad Database Change

"Store everything as JSON because it is flexible."

Future querying ignored.

---

# Decision Quality Questions

Before accepting architecture:

Ask:

What problem exists?

What options exist?

Why this option?

What becomes harder?

Can future engineers understand?

---

# Warning Signs

Poor decisions usually contain:

* no problem statement
* no alternatives
* trend-based choices
* ignored tradeoffs
* unnecessary rewrites

---

# Final Principle

Architecture decisions are not about proving intelligence.

They are about creating systems that continue working.