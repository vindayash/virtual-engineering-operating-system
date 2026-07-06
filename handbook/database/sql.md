# SQL Standards

SQL communicates with relational databases.

Queries should be correct, readable and efficient.

---

# SQL Philosophy

Good SQL should be:

* understandable
* predictable
* intentional

A clever query nobody understands becomes a future problem.

---

# Existing Project Rule

Existing SQL style has priority.

Before changing:

Understand:

* naming conventions
* query style
* ORM usage
* database engine behavior

Do not rewrite working queries unnecessarily.

---

# Readability First

Optimize for understanding.

Good SQL clearly shows:

* selected data
* relationships
* filtering
* ordering

---

# Select Required Columns

Avoid:

SELECT *

in production queries.

Prefer:

SELECT
id,
email,
created_at

Retrieve what is needed.

---

# Filtering

Filters should be explicit.

Good:

WHERE status = 'ACTIVE'

Avoid filtering unnecessary data in application code.

Let databases do database work.

---

# Joins

Use joins intentionally.

Understand:

INNER JOIN

LEFT JOIN

Choose based on required behavior.

---

# Avoid Hidden Expensive Queries

Be careful with:

* unnecessary joins
* large scans
* repeated queries

Small development data hides problems.

---

# Query Parameters

Never build SQL using string concatenation.

Bad:

"SELECT * FROM users WHERE id=" + user_id

Use parameterized queries.

Protect against injection.

---

# Aggregations

Use database aggregation when appropriate.

Examples:

COUNT

SUM

AVG

Avoid loading thousands of rows only to calculate in code.

---

# Ordering

Do not assume default ordering.

If order matters:

Use ORDER BY.

Databases do not guarantee natural order.

---

# Pagination

Large datasets need pagination.

Avoid:

return all records

Use:

* limit offset
* cursor pagination

depending on requirements.

---

# Transactions

Multiple dependent changes should use transactions.

Data consistency matters.

---

# Query Formatting

Format complex queries clearly.

Readable:

SELECT

FROM

WHERE

GROUP BY

ORDER BY

Each section should be easy to find.

---

# Naming

Use meaningful aliases.

Good:

users u

orders o

Avoid confusing shortcuts.

---

# NULL Handling

Understand NULL behavior.

NULL means unknown or missing.

Handle intentionally.

---

# Database Functions

Database functions are useful.

Use them when:

* they improve performance
* they simplify queries

Avoid hiding too much logic inside the database.

---

# Stored Procedures

Use when project architecture requires them.

Do not introduce automatically.

Application ownership should remain clear.

---

# ORM Generated SQL

ORM does not remove SQL responsibility.

Understand generated queries.

Watch for:

* N+1 problems
* unnecessary joins
* inefficient filters

---

# Query Optimization

Before optimizing:

Measure.

Use:

* query plans
* execution times
* database metrics

Guessing creates complexity.

---

# Index Awareness

Understand available indexes.

Queries and indexes work together.

---

# Data Modification

Be careful with:

UPDATE

DELETE

Always verify conditions.

Missing WHERE can damage data.

---

# Production Queries

Before running manual production queries:

Verify:

* database target
* impact
* backup strategy when needed

Production data deserves caution.

---

# Security

Protect:

* credentials
* sensitive fields
* user data

Only access what is required.

---

# Warning Signs

Review SQL when:

* queries are impossible to read
* SELECT * exists everywhere
* application filters huge datasets
* query changes are made without measurement

---

# SQL Checklist

Before completion:

[ ] Query is readable

[ ] Only required data selected

[ ] Inputs are safe

[ ] Index usage considered

[ ] Large data considered

---

# Final Principle

SQL should clearly describe the data you need.

Make the database work efficiently.

Make humans understand easily.