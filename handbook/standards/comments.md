# Comments

Comments explain context that code cannot express.

Good comments reduce confusion.

Bad comments create maintenance problems.

---

# Comment Philosophy

Code should explain:

"What is happening?"

Comments should explain:

"Why is this happening?"

Do not use comments to fix unclear code.

---

# Existing Project Rule

Existing commenting style has priority.

Before changing:

Understand:

* documentation patterns
* team expectations
* codebase style

Do not rewrite comments unnecessarily.

---

# Prefer Clear Code First

Before adding a comment ask:

"Can better naming make this obvious?"

Improve code first.

Comment when needed.

---

# Good Comments

Good comments explain:

* decisions
* tradeoffs
* unusual behavior
* external constraints

Example:

Why a workaround exists.

---

# Bad Comments

Avoid:

# increase count by one

count += 1

The code already explains this.

---

# Explain Why

Good:

# Provider allows maximum 100 records per request,

# so batching is required.

The reason matters.

---

# Business Rules

Comment unusual business rules.

Example:

# Orders cannot be cancelled after shipment

# because invoices are generated externally.

Context prevents mistakes.

---

# Complex Algorithms

Document:

* approach
* assumptions
* limitations

Do not force readers to reverse engineer.

---

# Security Decisions

Explain security-sensitive choices.

Examples:

* permission restrictions
* validation decisions
* encryption behavior

---

# Workarounds

Always explain workarounds.

Include:

* reason
* limitation
* removal condition

---

# TODO Comments

TODOs must have context.

Bad:

TODO fix later

Good:

TODO: Replace temporary provider after migration completes.

---

# Avoid Dead Code

Do not comment old code.

Bad:

# old_function()

Remove it.

Version control stores history.

---

# Avoid Misleading Comments

Wrong comments are dangerous.

Update comments when behavior changes.

---

# Documentation Comments

Public interfaces may need:

* purpose
* parameters
* expected behavior

Follow language conventions.

---

# Generated Code

Mark generated sections clearly.

Avoid editing generated output accidentally.

---

# API Documentation

Document:

* behavior
* contracts
* important edge cases

Not internal implementation.

---

# Configuration Comments

Useful for explaining:

* environment values
* operational choices

Avoid obvious repetition.

---

# Comments During Debugging

Remove temporary debugging comments before completion.

Do not leave investigation notes forever.

---

# Comment Quantity

More comments do not mean better documentation.

Useful comments matter.

---

# Warning Signs

Review comments when:

* every line has explanation
* comments disagree with code
* unclear code depends on comments
* old commented code remains

---

# Comment Checklist

Before completion:

[ ] Comment explains why

[ ] Code is already readable

[ ] No dead code remains

[ ] TODO has context

[ ] Comments match behavior

---

# Final Principle

A good comment preserves knowledge.

It explains the reason future engineers cannot see.