# Code Style

Code style defines how code should be written and organized.

Readable code is easier to maintain than clever code.

---

# Code Style Philosophy

Good code should be:

* understandable
* predictable
* consistent
* maintainable

Optimize for humans first.

Computers already understand complexity.

---

# Existing Project Rule

Existing style has priority.

Before changing:

Understand:

* formatting rules
* conventions
* team preferences
* tooling

Do not rewrite files only to match personal preference.

Consistency beats preference.

---

# Readability First

Code is read more often than written.

Prefer:

clear

over

clever

A simple solution understood by everyone is valuable.

---

# Follow Language Standards

Use accepted ecosystem conventions.

Examples:

Python:

PEP8

JavaScript:

project formatter rules

Do not invent unnecessary styles.

---

# Formatting

Formatting should be automated when possible.

Use tools like:

* formatters
* linters
* IDE configuration

Avoid manual style debates.

---

# Consistency

Follow surrounding code.

If a project uses a pattern:

Understand before changing.

A mixed codebase is harder to maintain.

---

# Function Size

Functions should have clear responsibility.

A function should answer:

"What does this do?"

If unclear:

consider splitting.

---

# Single Responsibility

A piece of code should have a focused purpose.

Avoid:

functions that:

* validate
* calculate
* save
* notify
* deploy

all together.

---

# Avoid Premature Abstraction

Do not create abstractions before they solve problems.

Duplication is sometimes better than the wrong abstraction.

---

# Simple Before Generic

Avoid:

building a framework inside the application.

Solve today's problem clearly.

Extend when patterns appear.

---

# Code Organization

Group code by:

* responsibility
* ownership
* purpose

Not random categories.

---

# Error Handling

Errors should be:

* intentional
* understandable
* visible

Avoid hiding failures.

---

# Magic Values

Avoid unexplained values.

Bad:

if status == 3

Good:

if status == OrderStatus.COMPLETED

---

# Complex Logic

Complex logic requires clarity.

Improve using:

* better naming
* smaller functions
* documentation when needed

---

# Comments

Comments explain why.

Code explains what.

Do not comment obvious behavior.

---

# Dead Code

Remove unused code.

Version control already keeps history.

Commented old code creates confusion.

---

# Performance Code

Performance optimizations should have reason.

Avoid making code unreadable for imaginary speed.

---

# Security

Readable code helps security.

Complex unclear code hides vulnerabilities.

---

# Generated Code

Generated code should be clearly identified.

Avoid manually editing generated files unless required.

---

# Refactoring

Improve code gradually.

Avoid rewriting working systems without clear benefit.

---

# Warning Signs

Review code when:

* only one person understands it
* simple changes are difficult
* abstractions hide everything
* naming requires explanation

---

# Code Style Checklist

Before completion:

[ ] Code follows existing style

[ ] Names explain purpose

[ ] Complexity is justified

[ ] Formatting is consistent

[ ] No unnecessary abstraction added

---

# Final Principle

Great code feels obvious after reading.

Write for the next engineer.

That engineer might be you.