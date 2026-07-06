# Playbook: Technical Decision

Technical decisions shape the future of a system.

Choose intentionally.

Not emotionally.

---

# Purpose

Make engineering decisions based on:

* requirements
* constraints
* evidence
* tradeoffs

Avoid trend-driven choices.

---

# Active Agents

Use:

* Architect Agent
* Backend Agent
* Database Agent
* Security Agent

---

# Primary Rule

Problem first.

Technology second.

Never start with a tool.

---

# Step 1: Define Problem

Identify:

What problem are we solving?

Why does it matter?

What happens if we do nothing?

---

# Step 2: Understand Context

Review:

* existing system
* team knowledge
* requirements
* constraints

A good choice depends on environment.

---

# Step 3: Identify Options

Compare realistic alternatives.

Example:

Need faster reads:

Options:

* query optimization
* indexes
* caching
* read replicas

---

# Step 4: Evaluate Tradeoffs

Every option has:

Benefits

Costs

Consider both.

---

# Evaluation Criteria

Review:

* simplicity
* maintainability
* performance
* security
* cost
* operational effort

---

# Existing System Impact

Before changing:

Ask:

What breaks?

What needs migration?

Who is affected?

---

# Complexity Cost

Every solution adds cost.

Consider:

* learning
* debugging
* operations
* maintenance

---

# Team Capability

Choose technology that can be:

understood

maintained

operated

---

# Scalability Decisions

Scale for realistic needs.

Avoid designing only for imaginary future problems.

---

# Security Impact

Evaluate:

* access control
* data protection
* vulnerabilities
* operational risks

---

# Dependency Impact

Adding technology adds ownership.

Consider:

* updates
* compatibility
* support

---

# Reversibility

Prefer decisions that can evolve.

Avoid unnecessary lock-in.

---

# Document Important Decisions

Use:

handbook/adr/

Record:

* decision
* alternatives
* reasoning
* consequences

---

# Good Decision Example

Problem:

Repeated reports are slow.

Analysis:

Database query takes 10 seconds.

Decision:

Optimize query and add index.

Why:

Solves measured problem with minimal complexity.

---

# Bad Decision Example

Problem:

Application might grow someday.

Decision:

Rewrite into microservices.

Issue:

No current requirement.

High complexity added.

---

# AI Behavior Rule

Claude must provide:

* reasoning
* alternatives
* tradeoffs

before recommending major changes.

---

# Avoid

Never choose because:

* popular company uses it
* technology is trending
* it looks more advanced

without matching requirements.

---

# Output Format

Return:

## Problem

What needs solving.

## Options

Possible solutions.

## Comparison

Tradeoffs.

## Recommendation

Chosen approach.

## Reason

Why this fits.

## Risks

What to watch.

---

# Final Principle

Good engineering decisions age well.

They solve real problems with appropriate complexity.