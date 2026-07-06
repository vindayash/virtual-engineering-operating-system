# Test Generator

Generate tests that protect important behavior.

Testing exists to create confidence.

Not just increase numbers.

---

# Purpose

Guide creation of:

* unit tests
* API tests
* integration tests
* regression tests

that provide real value.

---

# Required References

Follow:

handbook/testing/

commands/review-code.md

project conventions

---

# Generation Rule

Before writing tests:

Understand:

What behavior must continue working?

Test behavior.

Not implementation details.

---

# Step 1: Identify Critical Behavior

Prioritize:

* business rules
* security logic
* data changes
* important workflows

---

# Step 2: Choose Test Type

Use the right level.

---

# Unit Tests

Use for:

* isolated logic
* calculations
* rules
* transformations

---

# API Tests

Use for:

* request behavior
* validation
* permissions
* responses

---

# Integration Tests

Use for:

* multiple components working together

---

# Regression Tests

Create after bugs.

Purpose:

Prevent the same issue returning.

---

# Test Naming

Names should explain behavior.

Good:

test_user_cannot_access_other_user_order

Bad:

test_function_1

---

# Test Structure

Prefer:

Arrange

Act

Assert

Setup.

Execute.

Verify.

---

# Success Cases

Test expected workflows.

Examples:

* valid request
* correct calculation
* successful operation

---

# Failure Cases

Test:

* invalid input
* missing permissions
* unavailable resources

Failures are important behavior.

---

# Security Tests

Prioritize:

* unauthorized access
* permission checks
* sensitive operations

---

# Database Tests

Verify:

* relationships
* constraints
* important queries

Avoid testing ORM internals.

---

# Mocking

Mock external systems when needed.

Examples:

* payment providers
* third-party APIs
* email services

---

# Avoid Over Mocking

Do not mock everything.

Tests should still verify real behavior.

---

# Coverage Rule

Coverage percentage is not the goal.

Useful protection is the goal.

---

# Existing Project Rule

Follow:

* testing framework
* fixtures
* naming style
* existing patterns

---

# AI Generation Rule

Claude should generate tests for:

important behavior first

Not every line.

---

# Avoid

Never create:

* tests with no assertions
* tests only checking mocks
* tests copying implementation
* useless coverage fillers

---

# Output Format

Return:

## Test Purpose

What is protected.

## Test Cases

Scenarios covered.

## Implementation

Test code.

## Missing Coverage

Important future tests.

---

# Final Principle

A good test fails when something important breaks.

Everything else is noise.