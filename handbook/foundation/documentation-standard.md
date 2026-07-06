# Documentation Standard

Documentation exists to transfer understanding.

Good documentation explains decisions, context and behavior.

Documentation is not a replacement for readable code.

---

# Purpose Of Documentation

Documentation should help engineers:

* understand systems faster
* make safer changes
* debug problems
* operate software
* understand past decisions

Documentation should reduce confusion.

---

# Documentation Philosophy

Document why.

Code explains what.

Tests explain expected behavior.

Documentation explains reasoning.

---

# Good Documentation

Good documentation explains:

* why something exists
* why decisions were made
* what trade-offs were accepted
* how components interact
* operational requirements
* important constraints

Example:

Good:

"User verification happens asynchronously because external identity providers can take several seconds to respond."

Bad:

"This function verifies users."

---

# Avoid Obvious Documentation

Do not document things already clear from code.

Avoid:

```python
# increase counter by one
counter += 1
```

Prefer:

```python
# Retry attempts are limited to prevent infinite external API calls
max_retries = 3
```

Explain intent.

Not syntax.

---

# Required Documentation

Every production project should maintain:

## README

Contains:

* project purpose
* setup instructions
* dependencies
* environment configuration
* running locally
* testing instructions
* deployment overview

---

## Architecture Documentation

Contains:

* system overview
* major components
* communication flow
* external dependencies
* important decisions

Focus on understanding.

Not unnecessary diagrams.

---

## API Documentation

Contains:

* endpoints
* request structure
* response structure
* authentication requirements
* important error cases

APIs are contracts.

Document contracts clearly.

---

## Environment Documentation

Document:

* required variables
* configuration options
* external services
* secrets requirements

Never document actual secrets.

---

## Operational Documentation

Production systems should explain:

* deployment process
* monitoring
* logging
* common failures
* recovery steps

Software must be operable.

---

# Architecture Decision Records

Important decisions should be recorded.

Record:

* decision made
* reason
* alternatives considered
* trade-offs

Future engineers need context.

Not just the final result.

---

# Comments Standard

Comments should explain:

* business rules
* unusual decisions
* limitations
* important warnings

Comments should not explain basic programming.

---

# Code Examples

Documentation examples should be:

* minimal
* realistic
* working
* maintained

Avoid large examples that become outdated.

---

# Documentation Updates

Documentation changes with the system.

When changing:

* architecture
* configuration
* workflows
* dependencies
* deployment

Update documentation.

Outdated documentation is worse than missing documentation.

---

# AI Documentation Rules

When Claude creates documentation:

DO:

* explain reasoning
* document decisions
* mention trade-offs
* keep information practical

DO NOT:

* generate unnecessary documents
* create fake complexity
* add enterprise templates without need
* write obvious explanations

---

# Documentation Review Checklist

Before adding documentation ask:

1. Does this help future engineers?
2. Does this explain something not obvious?
3. Will this reduce confusion?
4. Will this help during production issues?

If no:

Do not add it.

---

# Final Principle

Documentation should make future maintenance easier.

More documentation is not better.

Useful documentation is better.