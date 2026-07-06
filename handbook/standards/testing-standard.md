# Testing Standard

Testing protects application behavior.

Tests should create confidence that changes are safe.

---

# Testing Philosophy

A good test should answer:

"Does the system behave correctly?"

Not:

"Did we increase a coverage number?"

Quality matters more than quantity.

---

# Existing Project Rule

Existing testing strategy has priority.

Before changing:

Understand:

* framework
* tools
* conventions
* coverage expectations

Do not rewrite test systems unnecessarily.

---

# Test Behavior

Test what the system does.

Avoid testing how it internally does it.

Implementation changes should not break correct behavior.

---

# Testing Priority

Prioritize:

1. Critical business rules

2. Security behavior

3. Important user flows

4. Data integrity

5. Failure handling

---

# Unit Tests

Use unit tests for:

* isolated logic
* calculations
* validation
* rules

They should be:

* focused
* fast
* understandable

---

# Integration Tests

Use integration tests for:

* component interaction
* database behavior
* API flows

They verify systems working together.

---

# End To End Tests

Use when validating:

* important complete journeys
* critical workflows

Do not test everything end-to-end.

Maintenance cost matters.

---

# Happy Path Testing

Test successful behavior.

Example:

User creates an order successfully.

Required but not enough.

---

# Failure Testing

Failures are expected.

Test:

* invalid input
* missing data
* permission denial
* external failures

---

# Security Testing

Verify:

* authentication
* authorization
* data access rules

A user should not access what they do not own.

---

# Mocking

Mock boundaries.

Good:

* external APIs
* payment providers
* email services

Avoid mocking your entire application.

---

# Test Data

Use meaningful test data.

Good:

customer_email

expired_subscription

Avoid unclear values.

---

# Test Independence

Tests should not depend on execution order.

Each test should be able to run alone.

---

# Test Names

Names should describe expectations.

Good:

test_user_cannot_delete_another_users_file

Bad:

test_delete

---

# Coverage

Coverage is information.

Not success.

High coverage with weak assertions is still weak testing.

---

# Avoid Testing Frameworks

Do not test:

* framework behavior
* library internals

Trust stable dependencies.

Test your logic.

---

# Regression Tests

When fixing bugs:

Consider adding tests.

Prevent the same issue from returning.

---

# Test Maintainability

Tests are code.

Maintain:

* readability
* simplicity
* organization

Bad tests slow development.

---

# Continuous Integration

Important tests should run automatically.

Broken builds should be visible.

---

# Performance Tests

Add performance tests when:

* speed is critical
* scale requirements exist
* previous issues happened

Do not guess.

---

# Warning Signs

Review tests when:

* nobody trusts failures
* changing implementation breaks everything
* coverage is high but bugs continue
* tests require constant rewriting

---

# Testing Checklist

Before completion:

[ ] Important behavior protected

[ ] Failure cases tested

[ ] Security considered

[ ] Tests are readable

[ ] Mocks used correctly

[ ] Coverage has meaning

---

# Final Principle

Tests are confidence tools.

Protect behavior.

Allow improvement.