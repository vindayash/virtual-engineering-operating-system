# Playbook: Production Issue

Production issues require calm investigation.

Protect users.

Protect data.

Restore reliability.

---

# Purpose

Resolve production problems through:

* investigation
* safe fixes
* verification
* prevention

Avoid panic changes.

---

# Active Agents

Use:

* Backend Agent
* Database Agent
* Security Agent
* Infrastructure knowledge

---

# Primary Rule

Understand impact first.

Do not randomly change production systems.

---

# Step 1: Identify Impact

Determine:

What is broken?

Who is affected?

When did it start?

How severe is it?

---

# Step 2: Stabilize System

First priority:

Reduce user impact.

Options:

* rollback
* disable failing feature
* temporary safe mitigation

---

# Step 3: Gather Evidence

Review:

* logs
* metrics
* errors
* deployments
* recent changes

Facts before assumptions.

---

# Step 4: Find Root Cause

Identify:

Why did this happen?

Avoid fixing only symptoms.

---

# Step 5: Create Safe Fix

Prefer:

minimal targeted fix

over:

large risky change

Production is not the place for experiments.

---

# Application Issues

Review:

* errors
* dependencies
* configuration
* recent commits

---

# Database Issues

Check:

* slow queries
* locks
* connections
* migrations
* data problems

Protect data first.

---

# Infrastructure Issues

Review:

* resources
* networking
* deployments
* environment changes

---

# Security Issues

If security related:

Follow:

handbook/security/vulnerability-handling.md

Protect access and data.

---

# Rollback Decision

Rollback when:

* fix is risky
* impact is high
* previous version is stable

Recovery matters.

---

# Hotfix Rules

Hotfixes should be:

* minimal
* reviewed when possible
* documented

Avoid unrelated improvements.

---

# Communication

Explain:

* current impact
* action being taken
* resolution status

Use facts.

---

# Verification

After fixing:

Confirm:

* issue resolved
* system healthy
* no new failures

---

# Monitoring

Watch after recovery:

* errors
* performance
* unusual behavior

---

# Root Cause Review

After incident:

Document:

* cause
* fix
* prevention

Improve system knowledge.

---

# Prevention

Consider:

* tests
* monitoring
* validation
* process improvements

Prevent repeat issues.

---

# Avoid Blame

Focus on:

system improvement

Not individual mistakes.

---

# AI Behavior Rule

Claude must:

* investigate before suggesting fixes
* prioritize stability
* avoid risky rewrites

---

# Avoid

Never immediately:

* rewrite modules
* change architecture
* upgrade dependencies
* modify database

without evidence.

---

# Output Format

Return:

## Impact

What happened.

## Evidence

Known information.

## Root Cause

Why it happened.

## Fix

Minimal solution.

## Prevention

Future improvement.

---

# Final Principle

Production incidents are solved through discipline.

Restore first.

Improve after.