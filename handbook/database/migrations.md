# Database Migrations

Migrations manage database change over time.

A database schema is history.

Treat changes carefully.

---

# Migration Philosophy

Applications evolve.

Data must survive.

Migrations should be:

* predictable
* reversible when possible
* reviewed
* safe

---

# Existing Project Rule

Existing migration strategy has priority.

Before changing:

Understand:

* migration tooling
* schema history
* deployment process
* production constraints

Never rewrite migration history casually.

---

# Always Use Migrations

Database changes should go through migrations.

Avoid manual production changes.

Migration history provides:

* tracking
* repeatability
* consistency

---

# Migration Tools

Follow framework standards.

Examples:

Django:

Django migrations

SQLAlchemy:

Alembic

Flask:

Flask-Migrate

Use existing ecosystem tools.

---

# Migration Ownership

A migration should clearly represent one change.

Examples:

Good:

Add user status column

Bad:

Random unrelated schema updates together

---

# Review Generated Migrations

Auto-generated does not mean correct.

Always review:

* added columns
* removed columns
* constraints
* indexes

before applying.

---

# Production Data Awareness

Development databases are small.

Production databases contain:

* real data
* large volume
* business history

Think before migrating.

---

# Adding Columns

Consider:

* nullable behavior
* default values
* existing rows

Adding required fields needs planning.

---

# Removing Columns

Removing data is risky.

Consider:

1. Stop using column

2. Deploy application

3. Remove column later

Avoid breaking running systems.

---

# Renaming Columns

Renames may appear as:

delete old column

create new column

Verify generated migrations.

Prevent accidental data loss.

---

# Data Migrations

Data migrations require extra care.

Consider:

* execution time
* rollback
* partial failures

Large updates may need batching.

---

# Index Migrations

Adding indexes on large tables can be expensive.

Understand:

* locking behavior
* database impact
* timing

---

# Constraint Changes

Adding constraints requires existing data validation.

Example:

Adding unique constraint:

Existing duplicates must be handled first.

---

# Rollback Thinking

Before applying:

Ask:

"What happens if deployment fails?"

Have a recovery plan.

---

# Migration Testing

Test migrations before production.

Verify:

* upgrade path
* application compatibility
* important data

---

# Backward Compatibility

For zero downtime systems:

New application version and old database may overlap.

Plan migrations carefully.

---

# Migration Ordering

Respect migration dependencies.

Do not manually reorder without understanding.

---

# Never Edit Applied Migrations

Avoid modifying migrations already applied by others.

Create new migrations instead.

History should remain stable.

---

# Secrets In Migrations

Never place:

* passwords
* credentials
* private keys

inside migration files.

---

# Large Tables

For large datasets:

Consider:

* batching
* background migration
* staged deployment

Avoid long production locks.

---

# Documentation

Document unusual migrations.

Explain:

* why
* risks
* special steps

---

# Warning Signs

Review migrations when:

* data is deleted casually
* generated files are never checked
* production changes happen manually
* rollback is impossible

---

# Migration Checklist

Before applying:

[ ] Migration reviewed

[ ] Data impact understood

[ ] Production size considered

[ ] Rollback considered

[ ] Tested safely

---

# Final Principle

Code can be redeployed.

Lost data may never return.

Respect migrations.