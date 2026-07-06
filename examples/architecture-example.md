# Architecture Example

Reference examples for making architecture decisions.

Architecture should solve problems.

Not demonstrate complexity.

---

# Goal

Design systems that are:

* understandable
* maintainable
* reliable
* appropriate for requirements

---

# Simple Architecture Example

Requirement:

Small business application.

Few developers.

Moderate traffic.

Good choice:

Single application.

Clear modules.

Reliable database.

Why:

Simple to build.

Simple to maintain.

---

# Overengineered Example

Same requirement.

Bad choice:

Multiple microservices.

Message queues.

Kubernetes.

Complex infrastructure.

Problem:

Complexity added before need exists.

---

# Monolith Example

Good monolith:

* clear modules
* separated responsibilities
* good boundaries

A monolith is not automatically bad.

---

# Microservice Example

Use when there are real needs:

* independent scaling
* independent teams
* deployment separation
* strong service boundaries

---

# Bad Microservice Example

Reason:

"Microservices are modern."

Problem:

Architecture chosen without requirement.

---

# Layer Example

Good:

API

↓

Business workflow

↓

Database

Clear responsibilities.

---

# Bad Layer Example

API

↓

Service

↓

Manager

↓

Processor

↓

Helper

↓

Repository

with each layer forwarding calls.

Problem:

Complexity without value.

---

# Service Layer Example

Good reason:

Order creation:

* validate inventory
* charge payment
* create shipment
* send notification

Service coordinates workflow.

---

# Bad Service Layer Example

UserService:

calls:

UserCRUD.create()

and does nothing else.

Remove unnecessary layer.

---

# Scaling Example

Problem:

Database query takes 8 seconds.

Good:

Analyze query.

Optimize.

Add index if needed.

---

Bad:

Immediately split database.

Create new services.

---

# Cache Example

Good:

Repeated expensive calculation.

Known invalidation rules.

Add cache.

---

Bad:

Application slow.

Add cache everywhere.

---

# Technology Decision Example

Good:

Problem:

Need relational consistency.

Decision:

Use relational database.

---

Bad:

Choose database because:

Popular company uses it.

---

# Dependency Example

Good:

Library solves complex maintained problem.

---

Bad:

Install package for five lines of simple code.

---

# Refactor Example

Good:

Improve small sections safely.

---

Bad:

Rewrite entire project because code looks old.

---

# Infrastructure Example

Good:

Start:

Simple deployment.

Monitoring.

Backups.

Grow as needed.

---

Bad:

Start with enterprise infrastructure without enterprise problems.

---

# Architecture Review Questions

Always ask:

What problem does this solve?

What complexity does it add?

Who maintains it?

Can we make it simpler?

---

# Final Principle

Great architecture is not impressive because it is complex.

It is impressive because it makes complexity disappear.