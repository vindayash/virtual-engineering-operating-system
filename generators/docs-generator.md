# Documentation Generator

Generate documentation that transfers knowledge.

Documentation should answer questions.

Not increase file count.

---

# Purpose

Guide creation of:

* README files
* architecture documents
* API documentation
* ADR records
* operational guides

---

# Required References

Follow:

templates/README-template.md

templates/ADR-template.md

commands/generate-docs.md

---

# Generation Rule

Before documenting:

Understand:

Who will read this?

What problem does this solve?

---

# Step 1: Identify Audience

Different readers need different information.

---

# Developers Need

Document:

* setup
* architecture
* workflows
* important decisions

---

# Operators Need

Document:

* deployment
* configuration
* recovery steps

---

# API Consumers Need

Document:

* endpoints
* authentication
* request/response behavior

---

# Step 2: Inspect Existing Docs

Before creating new files:

Check:

Can existing docs improve?

Avoid duplicates.

---

# README Generation

Include:

* purpose
* setup
* configuration
* running project
* testing
* important notes

---

# Architecture Documentation

Explain:

Why things exist.

Include:

* system overview
* important components
* tradeoffs

---

# ADR Generation

Create ADRs for:

* database choices
* architecture changes
* technology decisions

Do not create ADRs for tiny choices.

---

# API Documentation

Document:

* endpoint purpose
* authentication
* request examples
* responses
* errors

---

# Environment Documentation

Document variables.

Never include:

* real secrets
* credentials
* private keys

---

# Deployment Documentation

Include:

* environments
* process
* important operational steps

---

# Security Documentation

Document:

* authentication approach
* authorization rules
* sensitive workflows

Avoid exposing attack details unnecessarily.

---

# Code Comments

Generate comments only when explaining:

Why something exists.

Avoid comments explaining obvious code.

---

# Example Usage

Add examples when they:

* reduce confusion
* speed onboarding

---

# Maintenance Rule

Prefer:

small accurate documentation

over:

large outdated documentation

---

# Existing Project Rule

Match:

* documentation style
* terminology
* structure

---

# AI Generation Rule

Claude must not:

* invent features
* guess missing architecture
* create fake instructions

Document reality.

---

# Avoid

Never generate:

* unnecessary documents
* duplicated explanations
* fake examples
* outdated assumptions

---

# Output Format

Return:

## Documentation Added

Files created/updated.

## Purpose

Why it exists.

## Audience

Who uses it.

## Maintenance Notes

What should stay current.

---

# Final Principle

Good documentation saves future investigation.

Write what future engineers will need.