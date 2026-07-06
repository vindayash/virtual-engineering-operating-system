# Code Review Standard

Code review improves software quality.

It is not a place for personal preference battles.

---

# Review Philosophy

A good review should improve:

* correctness
* security
* maintainability
* reliability

without creating unnecessary change.

---

# Existing Code Rule

Existing code has priority.

Before suggesting changes:

Understand:

* current patterns
* architecture
* constraints
* project history

Do not rewrite code just because another style exists.

---

# Respect Working Systems

Working production code has value.

Do not replace:

simple working solutions

with:

complex theoretical improvements

without clear benefit.

---

# Review Priorities

Review in this order:

1. Bugs

2. Security issues

3. Data problems

4. Performance problems

5. Maintainability

6. Style

Style is not the first concern.

---

# Correctness Review

Check:

* edge cases
* error handling
* assumptions
* unexpected inputs

The code should behave correctly.

---

# Security Review

Look for:

* exposed secrets
* missing authorization
* unsafe input handling
* sensitive data leaks

Security issues have high priority.

---

# Architecture Review

Ask:

Does this structure solve the current problem?

Avoid:

adding patterns only because they exist.

---

# Performance Review

Before suggesting optimization:

Verify:

* actual problem
* expected scale
* impact

Avoid premature optimization.

---

# Simplicity Review

Prefer:

simple readable solutions

over:

complex abstractions

unless complexity is justified.

---

# Consistency Review

Follow existing project style.

A consistent codebase is easier to maintain.

---

# Avoid Personal Preference Changes

Avoid comments like:

"I prefer this pattern."

Suggest changes because they provide value.

---

# Refactoring Suggestions

Before suggesting refactoring:

Ask:

Does this improve:

* readability?
* safety?
* maintainability?

If not, avoid it.

---

# Dependency Review

Question new dependencies.

Ask:

* Is it maintained?
* Is it needed?
* Can existing tools solve this?

Dependencies create responsibility.

---

# Database Review

Check:

* migrations
* queries
* indexes
* transactions
* data safety

Protect stored information.

---

# API Review

Check:

* contracts
* validation
* errors
* compatibility

APIs affect other systems.

---

# Test Review

Review:

* meaningful coverage
* failure cases
* important workflows

Do not demand tests without purpose.

---

# Documentation Review

Request documentation when:

* decisions are not obvious
* future developers need context

Avoid documenting obvious code.

---

# Review Communication

Be specific.

Bad:

"This is bad."

Good:

"This can fail when the user does not exist."

Explain reasoning.

---

# Existing Project Improvements

For legacy projects:

Prefer:

small safe improvements

over:

large rewrites

---

# When Not To Change Code

Do not modify when:

* no clear benefit exists
* risk is higher than value
* change only satisfies preference

---

# Warning Signs

Review review behavior when:

* every file gets rewritten
* suggestions add unnecessary patterns
* style dominates discussions
* existing constraints are ignored

---

# Review Checklist

Before suggesting change:

[ ] Existing approach understood

[ ] Issue is real

[ ] Benefit is clear

[ ] Risk considered

[ ] Simpler option checked

---

# Final Principle

Good reviews protect systems.

They improve code without creating unnecessary complexity.