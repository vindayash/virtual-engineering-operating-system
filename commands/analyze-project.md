# Command: Analyze Project

Analyze an existing project before making any changes.

This command creates understanding.

Not modifications.

---

# Purpose

Understand:

* architecture
* technology stack
* structure
* patterns
* risks

before writing or changing code.

---

# Required Behavior

Read first.

Analyze second.

Suggest third.

Never modify immediately.

---

# Active Agents

Use:

* Architect Agent
* Backend Agent
* Database Agent
* Security Agent

as required.

---

# Step 1: Project Overview

Identify:

* language
* framework
* application type
* purpose
* major components

Explain what exists.

---

# Step 2: Folder Structure Analysis

Review:

* organization
* responsibilities
* framework alignment

Do not judge only by personal preference.

---

# Step 3: Architecture Analysis

Understand:

* design patterns
* module boundaries
* dependencies
* data flow

Reference:

handbook/architecture/

---

# Step 4: Backend Analysis

Review:

* APIs
* validation
* error handling
* business logic placement

Reference:

handbook/backend/

---

# Step 5: Framework Analysis

Identify framework.

Apply relevant rules:

handbook/frameworks/

Examples:

FastAPI

Django

Flask

Respect framework conventions.

---

# Step 6: Database Analysis

Review:

* database choice
* models
* queries
* migrations
* relationships

Reference:

handbook/database/

---

# Step 7: Security Analysis

Review:

* authentication
* authorization
* secrets
* data handling

Reference:

handbook/security/

---

# Step 8: Infrastructure Analysis

Review:

* deployment
* environment
* Docker
* CI/CD
* monitoring

Reference:

handbook/infrastructure/

---

# Existing Code Protection

Do not suggest rewriting because:

* different style exists
* newer technology exists
* another pattern is popular

Find actual problems.

---

# Identify Strengths

Always identify:

* what works well
* good decisions
* existing patterns worth keeping

Do not only criticize.

---

# Identify Risks

Separate:

Critical issues:

Must fix.

Improvements:

Worth considering.

Preferences:

Optional.

---

# Output Format

Return:

## Project Summary

What exists.

## Current Architecture

How it works.

## Strengths

Good existing decisions.

## Risks

Important concerns.

## Recommended Improvements

Prioritized actions.

## Avoid Changing

Things that should remain.

---

# Restrictions

Do not:

* rewrite files
* create new architecture
* install dependencies
* restructure folders

during analysis.

---

# Final Principle

Understand before improving.

A correct analysis prevents unnecessary changes.