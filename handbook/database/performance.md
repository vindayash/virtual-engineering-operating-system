# Database Performance

Database performance should be improved through understanding and measurement.

Optimization without evidence creates complexity.

---

# Performance Philosophy

Performance work follows:

Measure

↓

Understand

↓

Optimize

Never optimize blindly.

---

# Existing System Rule

Existing database behavior has priority.

Before changing:

Understand:

* workload
* traffic patterns
* data size
* current bottlenecks

Do not rewrite working systems based on assumptions.

---

# First Rule

Find the real problem.

Slow applications are not always caused by databases.

Measure before changing.

---

# Query Measurement

Analyze:

* execution time
* query plans
* scanned rows
* database metrics

Use evidence.

---

# Avoid Guessing

Bad:

Application slow

↓

Add indexes

↓

Rewrite queries

Good:

Application slow

↓

Find slow operation

↓

Fix specific issue

---

# Select Only Needed Data

Avoid loading unnecessary information.

Bad:

Fetch complete objects

Use only one field

Retrieve what is required.

---

# Avoid N+1 Queries

Watch for:

Loop

↓

Database query

↓

Repeat

Example problem:

100 users

=

101 queries

Optimize using proper loading strategies.

---

# ORM Awareness

ORMs generate queries.

Understand:

* lazy loading
* eager loading
* joins
* generated SQL

ORM does not remove database knowledge.

---

# Pagination

Large datasets require pagination.

Avoid:

return everything

Use:

* limit offset
* cursor pagination

based on requirements.

---

# Index Usage

Indexes improve reads.

But affect:

* writes
* storage
* maintenance

Create indexes intentionally.

---

# Large Data Processing

Avoid loading millions of rows into memory.

Consider:

* batching
* streaming
* background processing

Process data safely.

---

# Aggregations

Use databases for suitable aggregations.

Examples:

COUNT

SUM

GROUP BY

Avoid unnecessary application processing.

---

# Caching

Caching solves repeated expensive work.

It does not fix bad design.

Before caching:

Understand why something is slow.

---

# Cache Strategy

Define:

* what is cached
* expiration rules
* invalidation strategy

Incorrect cache creates incorrect systems.

---

# Connection Management

Manage database connections properly.

Avoid:

* connection leaks
* unlimited connections
* inefficient pooling

---

# Write Performance

Optimize writes by understanding:

* transactions
* indexes
* batch operations

Do not sacrifice correctness.

---

# Background Processing

Move expensive work outside requests when needed.

Examples:

* reports
* large exports
* data processing

---

# Database Scaling

Scale when required.

Options:

* query optimization
* indexing
* caching
* replicas
* partitioning

Use complexity gradually.

---

# Read Replicas

Useful for:

* read-heavy workloads

Consider:

* replication delay
* consistency requirements

---

# Partitioning

Partition only when data size requires it.

It adds operational complexity.

---

# Monitoring

Production databases need visibility.

Monitor:

* slow queries
* resource usage
* errors
* connection usage

---

# Performance Testing

Test with realistic data.

Small local databases hide real issues.

---

# Security Balance

Never improve performance by removing:

* validation
* permissions
* data protection

Fast but unsafe is failure.

---

# Warning Signs

Review performance when:

* optimization happens without measurement
* caches hide broken queries
* memory usage keeps growing
* database load is unexplained

---

# Performance Checklist

Before optimizing:

[ ] Bottleneck measured

[ ] Query understood

[ ] Data size considered

[ ] Simple fixes checked

[ ] Complexity justified

---

# Final Principle

Performance engineering is investigation.

Measure first.

Optimize what matters.