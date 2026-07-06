# Database Transactions

Transactions protect data when multiple operations must succeed together.

They maintain consistency.

---

# Transaction Philosophy

A transaction represents:

"Everything succeeds."

or

"Nothing changes."

Partial success can corrupt systems.

---

# Existing Project Rule

Existing transaction handling has priority.

Before changing:

Understand:

* ORM behavior
* transaction boundaries
* database rules
* existing patterns

Do not modify transaction flow casually.

---

# When To Use Transactions

Use transactions when operations depend on each other.

Examples:

Create order

*

Reduce inventory

Transfer money

*

Record transaction

---

# When Transactions Matter

Ask:

"If step 2 fails, should step 1 remain?"

If no:

Use a transaction.

---

# Simple Operations

Not every query needs manual transaction handling.

Frameworks and ORMs may already manage simple cases.

Understand existing behavior.

---

# Transaction Boundaries

Keep boundaries clear.

Know:

* where transaction starts
* what happens inside
* where commit occurs

Random commits create problems.

---

# Commit Responsibility

Avoid commits scattered everywhere.

Bad:

Function A commits

Function B commits

Function C commits

Hard to control failures.

---

# Rollbacks

Failures should leave data safe.

Plan:

* exception handling
* rollback behavior
* recovery

---

# Business Workflows

Transactions usually belong around workflows.

Example:

Service layer:

Begin transaction

↓

Multiple changes

↓

Commit

---

# Avoid Long Transactions

Keep transactions short.

Long transactions can cause:

* locks
* contention
* performance issues

---

# External API Calls

Be careful calling external systems inside transactions.

Example:

Open transaction

↓

Call payment API

↓

Wait

This can hold database resources unnecessarily.

---

# External Side Effects

Database rollback cannot undo:

* emails
* API calls
* messages sent

Design carefully.

---

# Idempotency

Important operations should handle retries safely.

Example:

Payment retry should not charge twice.

---

# Isolation Levels

Understand isolation when needed.

Issues include:

* dirty reads
* race conditions
* conflicts

Use appropriate database behavior.

---

# Race Conditions

Transactions help protect concurrent operations.

Consider:

* locks
* constraints
* atomic updates

when multiple users modify data.

---

# Atomic Updates

Prefer database-level atomic operations when needed.

Avoid:

read value

change value

save

when concurrency matters.

---

# Framework Usage

Follow framework patterns.

Examples:

Django:

transaction.atomic()

SQLAlchemy:

session transactions

Use correctly.

---

# Error Handling

Do not swallow transaction errors.

Bad:

try:

```
save()
```

except:

```
pass
```

Failures should be visible.

---

# Testing Transactions

Test:

* partial failures
* rollback behavior
* concurrent cases when required

Critical data needs confidence.

---

# Warning Signs

Review transactions when:

* data becomes inconsistent
* commits exist everywhere
* failures leave partial records
* external calls happen during transactions

---

# Transaction Checklist

Before completion:

[ ] Required operations grouped

[ ] Rollbacks considered

[ ] Commit location clear

[ ] External effects handled safely

[ ] Failure scenarios tested

---

# Final Principle

Transactions protect trust.

A system should never leave important data halfway finished.