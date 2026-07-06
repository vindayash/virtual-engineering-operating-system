# Playbook: New Project

Create a new project with intentional decisions.

Start simple.

Design for maintainability.

---

# Purpose

Guide creation of new systems that are:

* understandable
* secure
* maintainable
* ready to evolve

Avoid unnecessary complexity.

---

# Active Agents

Use:

* Architect Agent
* Backend Agent
* Database Agent
* Security Agent

---

# Step 1: Understand Requirements

Before choosing technology:

Identify:

* problem being solved
* users
* expected usage
* constraints
* timeline

Requirements drive architecture.

---

# Step 2: Define System Scope

Clarify:

What belongs in the system?

What does not?

Avoid building unnecessary features.

---

# Step 3: Choose Architecture

Follow:

handbook/architecture/

Prefer:

simple architecture first

Avoid:

complex distributed systems without need.

---

# Step 4: Choose Technology

Technology decisions should consider:

* requirements
* team knowledge
* maintenance
* ecosystem

Do not choose tools because they are trending.

---

# Backend Setup

Follow:

handbook/backend/

handbook/framework/

Use framework conventions.

---

# Project Structure

Create structure based on:

* framework standards
* project size
* expected growth

Avoid enterprise structures for small projects.

---

# Database Selection

Follow:

handbook/database/

Choose based on:

* data model
* relationships
* queries
* consistency needs

---

# API Design

Plan:

* endpoints
* validation
* errors
* authentication

APIs become contracts.

---

# Security Setup

Apply:

handbook/security/

Start with:

* secure configuration
* authentication strategy
* authorization model
* secret handling

---

# Configuration

Prepare:

* environments
* settings
* secret management

Do not hardcode configuration.

---

# Error Handling

Create consistent approach.

Include:

* custom exceptions when useful
* safe responses
* logging

---

# Testing Setup

Add practical testing.

Prioritize:

* important logic
* security
* critical workflows

---

# Documentation

Create:

* README
* setup instructions
* important decisions

Avoid unnecessary documents.

---

# Infrastructure Planning

Start with what is needed.

Add:

* CI/CD
* monitoring
* scaling

when requirements justify.

---

# Dependency Selection

Before adding packages:

Ask:

Do we need this?

Keep dependency list intentional.

---

# ADR Creation

Record important choices.

Examples:

* database selection
* architecture style
* authentication approach

---

# Avoid Starting With

Do not automatically add:

* microservices
* Kubernetes
* complex abstractions
* unnecessary layers

---

# Completion Checklist

Before first release:

[ ] Requirements understood

[ ] Architecture justified

[ ] Security considered

[ ] Database planned

[ ] Configuration externalized

[ ] Documentation exists

---

# Final Principle

A good new project starts simple.

Complexity can be added later.

Removing complexity is harder.