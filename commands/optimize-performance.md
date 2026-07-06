# Command: Optimize Performance

Improve system performance using evidence.

Optimization should solve measured problems.

Not imagined ones.

---

# Purpose

Identify and improve:

* slow operations
* inefficient queries
* resource usage
* scalability limits

while preserving correctness.

---

# Required Behavior

Measure first.

Understand second.

Optimize third.

Never optimize blindly.

---

# Active Agents

Use:

* Backend Agent
* Database Agent
* Architect Agent
* Reviewer Agent

when required.

---

# Step 1: Understand Problem

Identify:

What is slow?

When is it slow?

Who is affected?

What changed?

Define the actual issue.

---

# Step 2: Measure

Collect evidence:

* response times
* query duration
* logs
* metrics
* resource usage

Data guides optimization.

---

# Step 3: Find Bottleneck

Determine source:

* database
* application logic
* network
* external services
* infrastructure

Fix the right layer.

---

# Backend Performance

Review:

* unnecessary processing
* repeated operations
* inefficient algorithms
* blocking workflows

Improve targeted areas.

---

# Database Performance

Analyze:

* slow queries
* indexes
* query plans
* data loading

Follow:

handbook/database/performance.md

---

# Avoid N+1 Problems

Check:

Repeated queries inside loops.

Fix using:

* optimized queries
* eager loading
* batching

depending on framework.

---

# Data Loading

Avoid:

loading everything

Prefer:

* pagination
* filtering
* streaming
* batching

---

# Caching

Caching is not the first solution.

Before caching:

Understand why something is slow.

---

# Cache Requirements

Before adding cache:

Define:

* cached data
* expiration
* invalidation
* consistency needs

---

# Infrastructure Scaling

Scale infrastructure after:

* fixing inefficient code
* optimizing database usage
* understanding load

---

# Avoid Premature Scaling

Do not immediately add:

* microservices
* Kubernetes
* queues
* replicas

without need.

---

# Memory Optimization

Check:

* large objects
* unnecessary storage
* data processing patterns

Optimize based on evidence.

---

# Background Processing

Move work async when:

* requests wait unnecessarily
* operations are long-running

Do not add queues automatically.

---

# Dependency Performance

Review external libraries when:

* they create bottlenecks
* alternatives provide clear benefits

---

# API Performance

Review:

* payload size
* serialization
* database access
* external calls

---

# External Services

Check:

* latency
* retries
* timeouts
* failure handling

External dependencies affect performance.

---

# Maintainability Rule

Do not make code unreadable for tiny performance gains.

Balance:

speed

*

clarity

---

# Security Rule

Never improve performance by removing:

* validation
* authorization
* security checks

Fast insecure systems fail.

---

# Verification

After optimization:

Compare before vs after.

Confirm improvement.

---

# AI Optimization Rule

Claude must explain:

* measured problem
* optimization reason
* expected improvement
* tradeoffs

---

# Must Avoid

Never automatically:

* add caching everywhere
* rewrite architecture
* add infrastructure complexity
* optimize without evidence

---

# Output Format

Return:

## Performance Issue

Observed problem.

## Evidence

Measurements or indicators.

## Root Cause

Why it happens.

## Optimization

Targeted solution.

## Tradeoffs

What changes.

---

# Final Principle

Performance engineering is investigation.

The fastest solution is fixing the correct problem.