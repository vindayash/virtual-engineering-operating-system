# Command: Refactor Safe

Improve existing code safely.

Refactoring should reduce complexity.

Not create new problems.

---

# Purpose

Improve:

* readability
* maintainability
* organization
* reliability

while preserving existing behavior.

---

# Required Behavior

Before refactoring:

Understand first.

Plan second.

Modify last.

---

# Active Agents

Use:

* Refactor Agent
* Reviewer Agent
* Architect Agent
* Security Agent

when required.

---

# Step 1: Understand Current Code

Analyze:

* purpose
* dependencies
* inputs
* outputs
* side effects

Never refactor unknown logic.

---

# Step 2: Identify Actual Problems

Find real issues:

* duplicated logic
* unclear responsibility
* unsafe behavior
* difficult maintenance

Do not refactor because of preference.

---

# Step 3: Preserve Behavior

Maintain:

* API responses
* database behavior
* integrations
* user workflows

A refactor should not surprise users.

---

# Step 4: Choose Small Improvements

Prefer:

small controlled changes

Avoid:

complete rewrites

Incremental improvement wins.

---

# Step 5: Check Existing Patterns

Follow:

* project style
* architecture
* naming
* conventions

Consistency matters.

---

# Safe Refactoring Examples

Good:

Extract repeated validation logic.

Good:

Simplify complex function.

Good:

Separate mixed responsibilities.

---

# Unsafe Refactoring Examples

Bad:

Rewrite entire application structure.

Bad:

Replace framework.

Bad:

Add patterns everywhere.

---

# Architecture Changes

Architecture changes require:

* clear reason
* migration plan
* risk analysis

Do not happen automatically.

---

# Service Extraction

Only extract services when:

* business workflows exist
* complexity requires separation

Avoid empty layers.

---

# Dependency Changes

Do not change dependencies unless:

* dependency causes problem
* security requires it
* replacement has clear value

---

# Database Refactoring

Be careful with:

* schema changes
* migrations
* data transformations

Protect existing data.

---

# API Refactoring

Preserve:

* request format
* response format
* compatibility

unless intentional change requested.

---

# Testing Before Changes

For risky refactors:

Create confidence first.

Understand existing behavior.

---

# After Refactoring

Verify:

* existing tests pass
* behavior unchanged
* complexity reduced

---

# Documentation

Document important structural changes.

Explain why.

---

# AI Refactoring Rule

Claude must show:

Before:

problem.

After:

improvement.

Reason:

why safer.

---

# Must Avoid

Never automatically:

* restructure complete projects
* rename everything
* introduce new architecture
* replace working solutions
* modify unrelated files

---

# Output Format

Return:

## Current Problem

What needs improvement.

## Refactor Plan

Small steps.

## Changes

Exact modifications.

## Behavior Impact

Should remain unchanged.

## Risk

Possible concerns.

---

# Final Principle

The safest refactor is invisible externally.

Users see the same system.

Engineers see better code.