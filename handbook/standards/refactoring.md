# Refactoring Standard

Refactoring improves existing code without changing behavior.

The goal is safer evolution.

Not rewriting.

---

# Refactoring Philosophy

Good refactoring should improve:

* clarity
* maintainability
* safety
* flexibility

while preserving existing behavior.

---

# Existing Code Rule

Existing working code has value.

Before changing:

Understand:

* purpose
* constraints
* dependencies
* history

Do not rewrite because another approach looks cleaner.

---

# First Understand

Before refactoring:

Read the code.

Understand:

* why it exists
* how it is used
* what depends on it

Changing unknown systems creates risk.

---

# Preserve Behavior

Refactoring should not unexpectedly change:

* API contracts
* database behavior
* user workflows
* integrations

Behavior changes are features.

Not refactoring.

---

# Small Changes First

Prefer:

small improvements

over:

large rewrites

Small changes are easier to review and recover.

---

# When To Refactor

Refactor when:

* code is difficult to change
* bugs happen repeatedly
* duplication creates problems
* responsibilities are unclear

There should be a reason.

---

# When Not To Refactor

Avoid refactoring because:

* style preference
* different pattern preference
* new technology excitement

Different does not mean better.

---

# Avoid Rewrite Instinct

Do not replace:

working simple code

with:

complex architecture

without measurable improvement.

---

# Legacy Code

Legacy code usually contains:

* business knowledge
* edge cases
* historical decisions

Respect it.

Improve gradually.

---

# Before Large Refactors

Identify:

* current behavior
* risks
* testing strategy
* migration path

Large changes need planning.

---

# Tests Before Refactoring

When possible:

Add tests before changing risky code.

Tests protect existing behavior.

---

# Reduce Complexity

Good refactoring removes unnecessary complexity.

It does not only add:

* layers
* patterns
* abstractions

---

# Extracting Functions

Extract when it improves:

* readability
* reuse
* responsibility separation

Do not split until code becomes harder to understand.

---

# Creating Abstractions

Create abstractions after patterns appear.

Not before.

Wrong abstraction is expensive.

---

# Removing Code

Remove:

* unused functions
* dead branches
* obsolete logic

Version control keeps history.

---

# Dependency Cleanup

Remove unused dependencies.

Every dependency creates:

* updates
* security concerns
* maintenance

---

# Performance Refactoring

Only optimize after:

measurement

or

clear evidence

Avoid imaginary performance improvements.

---

# Database Refactoring

Be extra careful.

Database changes affect:

* stored data
* migrations
* external systems

Plan changes.

---

# API Refactoring

Maintain compatibility.

Consider:

* clients
* integrations
* versioning

Breaking APIs creates downstream problems.

---

# Documentation

Document important structural changes.

Explain why the change happened.

---

# Code Review

Refactoring should be easy to review.

Avoid mixing:

feature changes

*

large cleanup

---

# Warning Signs

Stop and review when:

* entire project is being rewritten
* changes have unclear benefits
* abstractions multiply
* tests cannot verify behavior

---

# Refactoring Checklist

Before refactoring:

[ ] Existing behavior understood

[ ] Clear improvement exists

[ ] Risk considered

[ ] Smaller change considered

[ ] Behavior preserved

---

# Final Principle

Great engineers do not rewrite everything.

They improve systems safely.