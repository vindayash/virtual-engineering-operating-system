# Django Signals

Signals allow parts of a Django application to react to events.

They should be used carefully.

Hidden behavior creates hidden complexity.

---

# Signal Philosophy

Signals are useful for decoupled reactions.

They should not hide important application workflows.

Explicit code is usually easier to understand.

---

# Existing Project Rule

Existing signal patterns have priority.

Before changing:

Understand:

* current signal usage
* side effects
* business dependencies

Do not remove or rewrite signals without understanding impact.

---

# When To Use Signals

Signals are useful for:

* independent reactions
* audit logging
* cache invalidation
* notifications
* tracking changes

when the original action does not depend on the result.

---

# When Not To Use Signals

Avoid signals for critical workflows.

Bad:

Order created

↓

Signal

↓

Payment processed

Important business flows should be explicit.

---

# Hidden Execution Problem

Signals make execution less obvious.

Example:

user.save()

may secretly:

* send emails
* update systems
* call APIs

Developers should understand consequences.

---

# Prefer Explicit Services

For workflows:

Prefer:

service.create_order()

inside:

* create order
* process payment
* send confirmation

The flow is visible.

---

# Signal Location

Standard:

apps/

└── users/

```
├── signals.py
```

Keep signals close to the app they support.

---

# Registering Signals

Register signals predictably.

Usually:

apps.py

Avoid random imports only to activate signals.

---

# Signal Responsibility

A signal should do one clear thing.

Good:

Create audit log after change.

Bad:

Handle entire business process.

---

# Signal Side Effects

Be careful with:

* database writes
* external calls
* background jobs

Unexpected side effects create bugs.

---

# Database Transactions

Signals may execute before transactions finish.

Understand:

* transaction timing
* rollback behavior
* consistency

Use transaction hooks when required.

---

# External Calls

Avoid direct external API calls in signals.

Prefer:

Signal

↓

Background job

when needed.

---

# Error Handling

Signal failures should be understood.

Ask:

Should original operation fail?

If yes:

A signal may not be the correct place.

---

# Performance

Signals run automatically.

Consider:

* execution cost
* database queries
* frequency

A common save operation can become expensive.

---

# Testing Signals

Test:

* expected triggers
* side effects
* failure behavior

Hidden code still requires tests.

---

# Avoid Signal Chains

Avoid:

Signal A

↓

updates model

↓

Signal B

↓

updates another model

Chains become difficult to debug.

---

# Documentation

Document important signals.

Explain:

* when they run
* why they exist
* what they change

---

# Warning Signs

Review signals when:

* nobody knows why something happens
* saving models triggers many actions
* debugging requires searching signals
* critical workflows are invisible

---

# Signal Checklist

Before adding:

[ ] Is decoupling needed?

[ ] Is this not a core workflow?

[ ] Are side effects safe?

[ ] Is execution understandable?

[ ] Is this tested?

---

# Final Principle

Signals are best for reactions.

Important business processes should be visible.