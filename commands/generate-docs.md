# Command: Generate Documentation

Create documentation that helps people understand and maintain systems.

Documentation should preserve knowledge.

Not create noise.

---

# Purpose

Generate useful documentation for:

* developers
* maintainers
* operators
* future decisions

Documentation should answer real questions.

---

# Required Behavior

Understand before documenting.

Document reality.

Do not invent architecture.

---

# Active Agents

Use:

* Architect Agent
* Backend Agent
* Database Agent
* Security Agent

when required.

---

# Step 1: Understand Project

Analyze:

* purpose
* architecture
* setup
* workflows
* dependencies

Documentation should match the system.

---

# Step 2: Identify Audience

Write for the reader.

Examples:

Developers:

How to work with code.

Operators:

How to run systems.

Users:

How to use features.

---

# README Documentation

Include when useful:

* project purpose
* setup instructions
* configuration
* running locally
* testing
* deployment notes

---

# Architecture Documentation

Explain:

* system structure
* important decisions
* data flow
* dependencies

Focus on why.

---

# API Documentation

Document:

* endpoints
* authentication
* requests
* responses
* errors

APIs are contracts.

---

# Database Documentation

Document when useful:

* important models
* relationships
* migrations
* special rules

Avoid repeating obvious schemas.

---

# Environment Documentation

Explain:

* required variables
* configuration
* setup steps

Never include real secrets.

---

# Deployment Documentation

Include:

* deployment process
* environments
* important operations

Keep production knowledge visible.

---

# Security Documentation

Document:

* authentication approach
* authorization model
* sensitive workflows

Do not expose secrets.

---

# Decision Documentation

Use ADRs for:

* important choices
* tradeoffs
* architecture changes

Follow:

handbook/adr/

---

# Comments vs Documentation

Comments:

Explain local reasoning.

Documentation:

Explain system knowledge.

Use the right place.

---

# Avoid Documentation Noise

Do not document:

* obvious code
* generated information
* unnecessary details

More pages do not mean better docs.

---

# Keep Documentation Updated

Outdated documentation creates risk.

Prefer:

small accurate docs

over:

large incorrect docs

---

# Existing Documentation Rule

Before creating new docs:

Check existing documentation.

Improve before duplicating.

---

# Examples

Include examples when they improve understanding.

Examples should be:

* realistic
* safe
* maintainable

---

# AI Documentation Rule

Claude must not:

* invent features
* guess architecture
* create fake instructions

Document only what exists.

---

# Must Avoid

Never:

* include credentials
* create unnecessary documents
* duplicate existing information
* hide important limitations

---

# Output Format

Return:

## Documentation Created

Files added or updated.

## Purpose

Why documentation exists.

## Content Summary

What was documented.

## Maintenance Notes

What should stay updated.

---

# Final Principle

Good documentation transfers understanding.

It explains what future engineers need to know.