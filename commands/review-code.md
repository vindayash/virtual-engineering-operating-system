# Command: Review Code

Review code to improve quality, reliability and security.

The goal is useful feedback.

Not unnecessary changes.

---

# Purpose

Analyze code for:

* bugs
* security risks
* maintainability issues
* performance problems

Prioritize real impact.

---

# Required Behavior

Understand before reviewing.

Review based on:

* project context
* existing patterns
* actual risks

Not personal preference.

---

# Active Agents

Use:

* Reviewer Agent
* Security Agent
* Database Agent
* Architect Agent

when required.

---

# Step 1: Understand Context

Before feedback:

Identify:

* framework
* architecture
* coding style
* project conventions

Context changes decisions.

---

# Step 2: Review Functionality

Check:

* incorrect behavior
* missing cases
* broken logic
* assumptions

Correctness comes first.

---

# Step 3: Review Security

Check:

* authentication
* authorization
* validation
* secrets
* sensitive data exposure

Security issues are high priority.

---

# Step 4: Review Data Safety

Analyze:

* database queries
* migrations
* transactions
* data changes

Protect information.

---

# Step 5: Review Performance

Look for evidence-based problems.

Examples:

* unnecessary queries
* repeated processing
* memory issues

Avoid premature optimization.

---

# Step 6: Review Maintainability

Consider:

* readability
* responsibilities
* duplication
* complexity

Suggest improvements only with value.

---

# Step 7: Review Tests

Check:

* important behavior coverage
* failure scenarios
* security cases

Do not chase meaningless coverage.

---

# Severity Levels

Classify findings.

---

# Critical

Must fix.

Examples:

* security vulnerability
* data corruption
* broken functionality

---

# Important

Should improve.

Examples:

* maintainability risks
* likely future issues

---

# Suggestion

Optional.

Examples:

* small improvements
* alternative approaches

---

# Avoid Preference Reviews

Do not comment only because:

"I prefer another style."

Existing consistency wins.

---

# Existing Code Protection

Avoid requesting:

* architecture rewrites
* framework changes
* unnecessary abstractions

unless clearly justified.

---

# Dependency Review

Check new dependencies.

Ask:

* needed?
* maintained?
* secure?

---

# Documentation Review

Recommend documentation only when:

* reasoning is unclear
* future maintenance benefits

---

# Positive Review

Mention:

* good patterns
* correct decisions
* improvements already present

Reviews should preserve good work.

---

# AI Review Rule

Claude must not:

* rewrite without request
* generate unrelated improvements
* ignore project constraints

Review first.

Change later.

---

# Must Avoid

Never:

* create noise comments
* enforce personal style
* suggest trends without reason
* ignore existing architecture

---

# Output Format

Return:

## Summary

Overall assessment.

## Critical Issues

Must fix.

## Important Improvements

Recommended.

## Suggestions

Optional.

## Good Decisions

Keep these.

---

# Final Principle

A valuable review makes code safer and easier to maintain.

It does not make code look like someone else wrote it.