# Playbook: Existing Project

Existing projects contain history and decisions.

Understand before changing.

---

# Purpose

Safely work with existing systems by learning:

* architecture
* patterns
* constraints
* business rules

before modifying code.

---

# Active Agents

Use:

* Architect Agent
* Backend Agent
* Database Agent
* Reviewer Agent
* Security Agent

---

# Primary Rule

Do not start by changing code.

First:

Explore.

Understand.

Document observations.

Then improve.

---

# Step 1: Identify Technology

Find:

* programming language
* framework
* database
* infrastructure
* dependencies

Understand the stack.

---

# Step 2: Understand Structure

Analyze:

* folders
* modules
* responsibilities
* boundaries

Do not judge structure without context.

---

# Step 3: Find Entry Points

Identify:

* application startup
* API routes
* commands
* workers
* scheduled tasks

Understand how execution begins.

---

# Step 4: Understand Data Flow

Trace:

Request

↓

Processing

↓

Database

↓

Response

Know the system behavior.

---

# Step 5: Learn Existing Patterns

Look for:

* naming conventions
* service usage
* error handling
* database access

Follow existing style.

---

# Step 6: Understand Database

Review:

* models
* schemas
* migrations
* relationships

Protect existing data.

---

# Step 7: Understand Security

Analyze:

* authentication
* authorization
* secrets
* permissions

Do not modify blindly.

---

# Step 8: Understand Infrastructure

Review:

* deployment
* environments
* configuration
* CI/CD

Applications include operations.

---

# Step 9: Identify Strengths

Record:

What works well?

What should stay?

Existing decisions often have reasons.

---

# Step 10: Identify Problems

Separate:

Critical:

Needs fixing.

Improvement:

Could help.

Preference:

Do not change.

---

# Making Changes

Before modifying:

Confirm:

* impact
* dependencies
* risk

Prefer small changes.

---

# Adding Features

New features should look native.

Follow:

* existing architecture
* existing naming
* existing patterns

---

# Fixing Bugs

Follow:

commands/fix-bug.md

Fix causes.

Avoid unrelated rewrites.

---

# Refactoring

Follow:

commands/refactor-safe.md

Improve gradually.

---

# Avoid

Never immediately:

* restructure folders
* replace frameworks
* introduce new architecture
* rewrite modules

---

# Documentation

Document discovered knowledge.

Especially:

* hidden behavior
* architecture decisions
* unusual patterns

---

# AI Behavior Rule

Claude must behave like a new senior engineer joining a team.

First understand.

Then contribute.

---

# Completion Checklist

Before changing:

[ ] Project purpose understood

[ ] Patterns identified

[ ] Data flow understood

[ ] Security reviewed

[ ] Impact considered

---

# Final Principle

Existing code is not just code.

It is accumulated decisions.

Respect them before improving them.