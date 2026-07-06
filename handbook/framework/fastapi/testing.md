# FastAPI Testing

Testing verifies application behavior.

Tests should create confidence that the system works correctly.

Testing is not about achieving numbers.

---

# Testing Philosophy

Good tests protect:

* business rules
* important workflows
* integrations
* failure scenarios

Tests should catch real problems.

Coverage percentage alone does not mean quality.

---

# Existing Project Rule

Existing testing patterns have priority.

Before changing:

Understand:

* current test structure
* tools
* fixtures
* conventions

Do not rewrite testing strategy unnecessarily.

---

# Test Structure

Recommended:

tests/

├── api/

├── services/

├── crud/

└── conftest.py

Organize tests by responsibility.

---

# Testing Priority

Priority order:

1. Business logic

2. Critical API flows

3. Data behavior

4. Failure cases

Do not only test happy paths.

---

# API Tests

API tests verify:

* endpoints
* request validation
* response contracts
* status codes
* authentication behavior

Example:

POST /users

should verify:

* valid creation
* invalid input
* duplicate user

---

# Service Tests

Services contain important logic.

Test:

* business rules
* workflows
* decision making
* external failure handling

Services usually deserve the most attention.

---

# CRUD Tests

Test CRUD when queries contain:

* custom filtering
* complex joins
* important behavior

Simple ORM operations do not always need isolated tests.

---

# Schema Tests

Test schemas when:

* validation is complex
* transformations exist
* contracts are critical

Avoid testing Pydantic itself.

---

# Dependency Overrides

Use FastAPI overrides.

Example:

app.dependency_overrides

Useful for replacing:

* database sessions
* authenticated users
* external services

during tests.

---

# Test Database

Tests should not affect production data.

Use:

* separate databases
* transactions
* isolated environments

Test data must be controlled.

---

# Fixtures

Use fixtures for:

* common setup
* reusable objects
* test users
* database preparation

Avoid overly complex fixture chains.

---

# Mocking

Mock external boundaries.

Good mocks:

* payment providers
* external APIs
* email services

Avoid mocking your entire application.

---

# Authentication Testing

Verify:

* authenticated requests
* unauthenticated requests
* invalid credentials
* permission failures

Security requires tests.

---

# Exception Testing

Test expected failures.

Examples:

UserNotFound

InvalidOrderState

PermissionDenied

Errors are part of application behavior.

---

# Background Task Testing

Test:

* execution logic
* failures
* retries
* side effects

Do not ignore async workflows.

---

# Integration Tests

Use integration tests for:

* important user flows
* database behavior
* service interaction

They provide confidence.

---

# Unit Tests

Use unit tests for:

* calculations
* rules
* isolated logic

Keep them simple.

---

# Avoid Testing Implementation

Avoid tests that depend on:

* internal function calls
* private structure
* unnecessary mocks

Test behavior.

Not implementation details.

---

# Test Naming

Names should explain behavior.

Good:

test_user_cannot_create_duplicate_email

Bad:

test_create_user

when purpose is unclear.

---

# Test Data

Use realistic data.

Avoid:

test

abc

123

when meaningful values improve understanding.

---

# Performance

Tests should stay reasonably fast.

Slow tests reduce usage.

Optimize test suites when needed.

---

# Continuous Integration

Automated tests should run before deployment.

Broken tests indicate risk.

---

# Testing Warning Signs

Review tests when:

* coverage is high but bugs escape
* changing code breaks unrelated tests
* tests duplicate implementation
* nobody trusts test results

---

# Testing Checklist

Before completing:

[ ] Critical workflows tested

[ ] Business rules protected

[ ] Failure cases included

[ ] External services controlled

[ ] Authentication tested

[ ] Tests are maintainable

---

# Final Principle

Good tests allow engineers to change code confidently.

Tests should protect behavior, not freeze implementation.