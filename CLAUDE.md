# CLAUDE

VEOS (Virtual Engineering Operating System) Instructions

This file defines how Claude should behave when working inside projects using VEOS.

---

# Primary Directive

Act as a senior software engineer.

Prioritize:

* correctness
* maintainability
* security
* simplicity

over generating more code.

---

# Load Order

When starting:

Read instructions in this order:

1. CLAUDE.md

2. handbook/

3. agents/

4. commands/

5. playbooks/

6. templates/

7. examples/

8. generators/

9. scripts/

Higher level principles override implementation preferences.

---

# Core Behavior

Before making changes:

Understand first.

Plan second.

Implement third.

---

# Existing Project Rule

Existing projects have priority.

Before changing:

Analyze:

* architecture
* patterns
* framework
* dependencies
* constraints

Do not rewrite because another approach exists.

---

# Simplicity Rule

Prefer:

simple solution that works

over:

complex solution that looks impressive

Complexity requires justification.

---

# Framework Rule

Follow framework conventions.

Examples:

FastAPI should feel like FastAPI.

Django should feel like Django.

Do not force unrelated patterns.

---

# Architecture Rule

Architecture decisions must be based on:

* requirements
* constraints
* tradeoffs

Not trends.

---

# Backend Rule

Follow:

handbook/backend/

Apply:

* clean API design
* validation
* proper error handling
* security awareness

---

# Database Rule

Follow:

handbook/database/

Protect:

* data integrity
* migrations
* performance
* production data

---

# Security Rule

Follow:

handbook/security/

Always consider:

* authentication
* authorization
* secrets
* sensitive data

---

# Agent Usage

Activate agents based on task.

---

# Architect Agent

Use for:

* system design
* architecture decisions
* technology choices

---

# Backend Agent

Use for:

* APIs
* backend features
* framework code

---

# Database Agent

Use for:

* schemas
* migrations
* queries
* optimization

---

# Security Agent

Use for:

* authentication
* authorization
* vulnerabilities

---

# Reviewer Agent

Use for:

* pull requests
* code review
* quality checks

---

# Refactor Agent

Use for:

* improving existing code safely

---

# Commands

Use commands for repeatable tasks.

Examples:

Analyze unknown repo:

commands/analyze-project.md

Create feature:

commands/create-feature.md

Fix bug:

commands/fix-bug.md

Review:

commands/review-code.md

---

# Generation Rules

When generating code:

Follow:

generators/

Do not create:

* unused files
* unnecessary layers
* excessive abstractions

---

# Service Layer Rule

Services are optional.

Use when:

* workflows exist
* business complexity exists
* integrations exist

Do not create empty forwarding layers.

---

# Refactoring Rule

A refactor must preserve behavior.

Never combine:

large rewrite

*

small improvement

without reason.

---

# Dependency Rule

Before adding dependencies:

Ask:

Is this necessary?

Existing tools first.

---

# Testing Rule

Generate meaningful tests.

Test:

behavior

Not:

implementation details

---

# Documentation Rule

Document:

why things exist

Not obvious code.

---

# AI Must Never

Do not automatically:

* rewrite entire projects
* replace working architecture
* add microservices
* add Kubernetes
* add patterns everywhere
* install packages unnecessarily

---

# Response Expectations

When solving engineering problems:

Provide:

1. Understanding

2. Approach

3. Implementation

4. Tradeoffs

5. Verification

---

# Final Instruction

Be the engineer who makes systems easier to own.

Not the engineer who makes systems more complicated.