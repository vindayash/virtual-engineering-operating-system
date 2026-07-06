# Architecture Decision Record Template

Architecture decisions should preserve reasoning.

Future engineers need to understand why choices were made.

---

# ADR Philosophy

An ADR captures:

Why was this decision made?

Not only:

What was chosen?

Context prevents unnecessary rewrites.

---

# When To Create ADRs

Create ADRs for important decisions.

Examples:

* framework selection
* database choices
* infrastructure changes
* authentication strategy
* major architecture patterns

Do not create ADRs for every small change.

---

# Existing Project Rule

Existing decisions have priority.

Before replacing architecture:

Search for:

* ADRs
* documentation
* comments
* historical context

Understand why before changing.

---

# ADR Format

Use the following structure.

---

# Title

Short decision summary.

Example:

Use PostgreSQL As Primary Database

---

# Status

Current state.

Options:

Proposed

Accepted

Deprecated

Replaced

---

# Context

Explain the situation.

Include:

* problem
* constraints
* requirements
* existing conditions

Why is a decision required?

---

# Decision

Describe what was chosen.

Be clear.

Example:

We will use PostgreSQL as the primary relational database.

---

# Alternatives Considered

List realistic alternatives.

Example:

Considered:

* PostgreSQL
* MySQL
* MongoDB

Explain why options were rejected.

---

# Reasoning

Explain why the decision makes sense.

Include:

* benefits
* tradeoffs
* constraints

No solution is perfect.

---

# Consequences

Every decision creates outcomes.

Document:

Positive:

What improves?

Negative:

What becomes harder?

---

# Risks

Mention possible problems.

Examples:

* scaling limitations
* operational complexity
* migration difficulty

---

# Migration Plan

When replacing existing systems:

Document:

* steps
* compatibility
* rollback strategy

---

# Review Date

Optional.

Useful when:

* technology changes quickly
* temporary decisions exist

---

# Example

Title:

Use Redis For Caching

Status:

Accepted

Context:

Repeated expensive queries affect response time.

Decision:

Use Redis cache for frequently accessed data.

Alternatives:

Database optimization only.

Application memory cache.

Consequences:

Improves read speed.

Adds infrastructure dependency.

---

# Updating ADRs

Do not delete history.

If a decision changes:

Create a new ADR.

Mark old decision as replaced.

---

# Avoid Fake ADRs

Do not create decisions after every small implementation detail.

ADRs should capture meaningful choices.

---

# Warning Signs

Create or review ADR when:

* nobody knows why technology exists
* architecture keeps changing
* old decisions are repeated
* rewrites happen without context

---

# ADR Checklist

Before completing:

[ ] Problem explained

[ ] Alternatives considered

[ ] Tradeoffs documented

[ ] Decision reasoning clear

[ ] Future readers understand why

---

# Final Principle

Architecture is a collection of decisions.

Record the reasoning, not just the result.