# Python Standard

Python code should be simple, readable, explicit and maintainable.

Python rewards clarity.

Write Python for humans first.

---

# Python Philosophy

Follow the spirit of Python:

Simple is better than complex.

Explicit is better than implicit.

Readability matters.

The goal is not clever Python.

The goal is understandable Python.

---

# Existing Project Rule

Existing Python style has priority.

Before changing code:

Understand:

* current structure
* formatting rules
* naming conventions
* framework patterns

Do not rewrite working Python because another style is preferred.

Consistency beats personal preference.

---

# Code Readability

Optimize for reading.

Good Python should make it clear:

* what happens
* why it happens
* where changes belong

Avoid:

* clever one-liners
* unnecessary magic
* complex expressions

Readable code wins.

---

# Naming

Names should communicate purpose.

Good:

calculate_invoice_total()

send_user_notification()

process_payment()

Bad:

handle()

process()

do_task()

unless context makes meaning obvious.

---

# Variables

Use meaningful names.

Good:

active_users = get_active_users()

Bad:

data = get_active_users()

Generic names hide meaning.

---

# Function Design

Functions should:

* do one clear thing
* have understandable inputs
* return predictable results

Avoid:

* hidden side effects
* excessive parameters
* unrelated responsibilities

---

# Function Size

Do not split functions only because of length.

Split when:

* responsibilities differ
* testing becomes difficult
* understanding becomes harder

Line count alone is not architecture.

---

# Classes

Use classes when they provide value.

Good reasons:

* shared state
* clear responsibility
* behavior grouping

Avoid classes that only contain unrelated static methods.

---

# Avoid Over Engineering

Do not automatically create:

* abstract base classes
* factories
* managers
* interfaces

Python does not require Java-style patterns.

Use abstractions when they solve problems.

---

# Imports

Keep imports:

* organized
* explicit
* understandable

Avoid:

from module import *

Wildcard imports hide dependencies.

---

# Error Handling

Handle exceptions intentionally.

Avoid:

try:
operation()

except Exception:
pass

Failures should be visible.

---

# Type Hints

Use type hints to improve understanding.

They should:

* document expectations
* catch mistakes
* improve maintainability

Avoid overly complex typing that reduces readability.

---

# Configuration

Do not hardcode:

* credentials
* environment values
* secrets

Use proper configuration management.

---

# Dependencies

Before adding packages:

Ask:

* is this necessary?
* is the library maintained?
* does Python already solve this?

Dependencies increase ownership.

---

# Formatting

Use automated formatting.

Prefer consistency over personal formatting style.

Do not manually argue about formatting.

---

# Comments

Comment why.

Not what.

Bad:

# loop users

Good:

# Process users in batches to avoid memory spikes

Explain decisions.

---

# Performance

Do not optimize Python prematurely.

First:

Measure.

Find bottleneck.

Improve targeted areas.

Readable correct code comes first.

---

# Data Processing

For large data:

Avoid:

* loading unnecessary data into memory
* inefficient loops
* repeated expensive operations

Choose tools based on data size.

---

# Security

Never:

* execute untrusted input
* expose secrets
* ignore dependency vulnerabilities

Validate external data.

---

# Testing

Python code should be testable.

Prefer:

* clear dependencies
* predictable functions
* limited side effects

Simple code is easier to test.

---

# Python Warning Signs

Review code when:

* understanding requires deep knowledge
* simple changes affect many places
* abstractions hide behavior
* everything is dynamic

Python should stay readable.

---

# Python Checklist

Before completing:

[ ] Code is readable

[ ] Names explain purpose

[ ] Errors are handled

[ ] Types improve clarity

[ ] No unnecessary abstraction

[ ] Existing style respected

---

# Final Principle

The best Python code looks obvious.

Simple Python maintained for years is better than clever Python nobody wants to touch.