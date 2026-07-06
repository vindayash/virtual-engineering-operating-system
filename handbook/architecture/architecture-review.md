# Architecture Review

Architecture review ensures systems remain simple, reliable, secure and maintainable.

The purpose is not to create perfect architecture.

The purpose is to prevent unnecessary complexity and unsafe decisions.

---

# Review Philosophy

Architecture should be reviewed based on:

* requirements
* constraints
* maintainability
* operational reality

Not based on:

* trends
* personal preference
* theoretical purity

Good architecture fits its environment.

---

# Understand Before Reviewing

Before suggesting architecture changes:

Understand:

* current system design
* business requirements
* existing constraints
* team capabilities
* production realities

Do not review without context.

---

# Existing System Review Rule

Existing systems should not be redesigned automatically.

First evaluate:

* what works today
* what causes problems
* what risks exist
* what changes are required

Prefer improving existing architecture.

Avoid replacing it.

---

# Requirement Validation

Every architecture decision must map to a requirement.

Ask:

What problem does this solve?

If the answer is unclear:

Do not add it.

---

# Complexity Review

For every added component ask:

Why does this exist?

Examples:

Cache:

What performance problem exists?

Queue:

What async requirement exists?

Microservice:

What ownership/scaling problem exists?

Database:

What data requirement exists?

No justification means unnecessary complexity.

---

# Simplicity Check

A good architecture should be explainable.

Review:

* Can a new engineer understand it?
* Are responsibilities clear?
* Is data flow obvious?
* Are dependencies understandable?

Confusing architecture creates risk.

---

# Boundary Review

Check whether components have clear responsibilities.

Avoid:

* mixed concerns
* unclear ownership
* circular dependencies
* duplicated responsibilities

Boundaries should reduce confusion.

---

# Dependency Review

Every dependency should justify itself.

Review:

* purpose
* maintenance status
* security impact
* replacement difficulty

Dependencies are long-term commitments.

---

# Data Review

Verify:

* data ownership
* consistency requirements
* transaction boundaries
* migration safety

Protecting data is more important than architectural style.

---

# Security Review

Every architecture must consider:

Authentication:

Who can access?

Authorization:

What actions are allowed?

Data:

What must be protected?

Failures:

What information leaks?

Security is part of architecture.

---

# Failure Review

Assume failure.

Review:

* database failures
* network failures
* external service failures
* invalid data
* infrastructure issues

Reliable systems expect problems.

---

# Scalability Review

Before scaling decisions:

Check:

* current measurements
* actual bottlenecks
* expected growth
* simpler solutions

Do not scale imaginary problems.

---

# Operational Review

A system must be operable.

Verify:

* logging
* monitoring
* deployment process
* configuration
* debugging ability

Building is only the beginning.

---

# Performance Review

Performance decisions require evidence.

Avoid:

* assumptions
* premature optimization
* unnecessary caching

Measure first.

Improve second.

---

# Migration Review

For large changes:

Prefer:

* incremental migration
* backward compatibility
* reversible changes

Avoid:

* complete rewrites
* risky deployments

Production safety matters.

---

# Architecture Warning Signs

Investigate when:

* simple changes require many files
* nobody understands a component
* debugging requires guessing
* deployments are risky
* failures are invisible

Architecture should reduce problems.

---

# Approval Checklist

Before approving architecture:

Confirm:

[ ] The problem is understood

[ ] Requirements justify decisions

[ ] Existing systems are respected

[ ] Complexity is necessary

[ ] Security is considered

[ ] Failures are handled

[ ] Data is protected

[ ] Operations are manageable

[ ] Future changes are possible

---

# Rejection Reasons

Reject architecture when:

* complexity has no purpose
* technology is chosen first
* existing systems are ignored
* operational cost is ignored
* security is an afterthought

---

# Final Principle

Architecture is not about designing the most advanced system.

Architecture is about making the right trade-offs for the current reality.