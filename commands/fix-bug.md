# Command: Fix Bug

Fix existing problems safely.

The goal is removing the defect.

Not rewriting the system.

---

# Purpose

Identify and fix bugs by understanding:

* cause
* impact
* correct behavior
* safest solution

---

# Required Behavior

Debug first.

Understand second.

Change last.

Never modify code before understanding the problem.

---

# Active Agents

Use:

* Backend Agent
* Database Agent
* Security Agent
* Refactor Agent

when needed.

---

# Step 1: Understand The Bug

Identify:

What is happening?

What should happen?

When does it happen?

What changed recently?

---

# Step 2: Reproduce The Issue

Before fixing:

Find:

* input causing issue
* failing flow
* error message
* affected component

A reproduced bug is easier to fix.

---

# Step 3: Find Root Cause

Do not only remove symptoms.

Understand:

* why failure happens
* where it originates
* what assumptions failed

---

# Step 4: Analyze Existing Code

Before changing:

Understand:

* current pattern
* dependencies
* expected behavior

Respect existing design.

---

# Step 5: Minimal Safe Fix

Prefer:

small targeted correction

over:

large rewrite

Fix the cause.

Not unrelated code.

---

# Avoid Guessing

Do not randomly change:

* configurations
* dependencies
* architecture

without evidence.

---

# Error Analysis

For errors:

Check:

* stack trace
* logs
* recent changes
* environment differences

Use facts.

---

# Database Bugs

Before fixing:

Consider:

* existing data
* migrations
* transactions
* constraints

Do not risk data loss.

---

# API Bugs

Check:

* request handling
* validation
* permissions
* response contracts

Avoid breaking clients.

---

# Security Bugs

Prioritize:

* authentication failures
* authorization issues
* data leaks
* secret exposure

Follow security rules.

---

# Dependency Bugs

Before upgrading:

Understand:

* compatibility
* breaking changes
* impact

Do not blindly update packages.

---

# Regression Prevention

After fixing:

Consider:

* adding tests
* improving validation
* documenting edge cases

Prevent repeat failures.

---

# Refactoring During Bug Fixes

Avoid mixing:

Bug fix

*

Large refactor

Separate concerns.

---

# Legacy Code Rule

Do not rewrite legacy code because a bug exists.

Fix safely.

Improve gradually.

---

# Verification

Confirm:

* original issue fixed
* existing behavior preserved
* related cases still work

---

# AI Fix Rule

Claude must explain:

* cause found
* change made
* why fix works

No unexplained modifications.

---

# Must Avoid

Never automatically:

* rewrite entire modules
* replace libraries
* redesign architecture
* remove validation
* hide errors

---

# Output Format

Provide:

## Problem

What is failing.

## Root Cause

Why it fails.

## Fix

Minimal required change.

## Impact

What changes.

## Verification

How to confirm.

---

# Final Principle

A good bug fix removes the problem.

A bad bug fix creates new ones.