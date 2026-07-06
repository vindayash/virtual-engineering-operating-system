# Django Testing

Testing verifies that Django applications behave correctly.

Tests should protect important behavior.

They should not exist only for coverage numbers.

---

# Testing Philosophy

Good tests create confidence.

Focus on:

* business rules
* user workflows
* permissions
* data integrity
* failure scenarios

Test behavior.

Not framework internals.

---

# Existing Project Rule

Existing testing patterns have priority.

Before changing:

Understand:

* test structure
* tools
* fixtures
* conventions

Do not rewrite test architecture unnecessarily.

---

# Test Structure

Recommended:

apps/

└── users/

```
└── tests/

    ├── test_models.py

    ├── test_views.py

    ├── test_services.py

    └── test_permissions.py
```

Organize by responsibility.

---

# What To Test First

Priority:

1. Business rules

2. Critical workflows

3. Permissions

4. Data behavior

5. API contracts

Important behavior deserves protection.

---

# Model Tests

Test:

* custom model methods
* constraints
* state behavior
* custom managers

Avoid testing Django ORM itself.

---

# View Tests

Test:

* request handling
* responses
* status codes
* authentication
* permissions

Views define external behavior.

---

# Serializer Tests

Test:

* validation rules
* required fields
* transformations
* hidden sensitive data

Do not test DRF internals.

---

# Service Tests

Services should test:

* workflows
* business decisions
* transactions
* external failure handling

Business logic needs confidence.

---

# Permission Tests

Always test:

* allowed users
* denied users
* ownership checks

Security requires negative testing.

---

# Celery Task Tests

Test:

* task execution
* failure handling
* retry behavior

Async does not mean untested.

---

# Factories

Use factories for reusable test data.

Examples:

UserFactory

OrderFactory

Avoid large duplicated setup.

---

# Fixtures

Use fixtures carefully.

Good:

shared environment setup.

Avoid:

large hidden test worlds.

Tests should remain understandable.

---

# Database Tests

Database tests should use isolated test databases.

Never run tests against production data.

---

# Transactions

Test transaction behavior when:

* multiple writes happen
* consistency matters
* failures can occur

---

# Mocking

Mock external systems.

Good:

* payment APIs
* email services
* third-party APIs

Avoid mocking Django itself unnecessarily.

---

# Integration Tests

Use integration tests for:

* important flows
* API behavior
* component interaction

They verify real behavior.

---

# Unit Tests

Use unit tests for:

* calculations
* rules
* isolated services

Keep them focused.

---

# Coverage

Coverage is a measurement.

Not the goal.

High coverage with weak tests creates false confidence.

---

# Test Names

Names should explain expectations.

Good:

test_user_cannot_access_other_user_order

Bad:

test_order

---

# Test Data

Use meaningful data.

Avoid:

abc

test

123

when realistic examples improve clarity.

---

# Performance

Tests should remain fast enough to run regularly.

Slow tests become ignored tests.

---

# Continuous Integration

Run tests automatically before deployment.

Tests protect changes.

---

# Warning Signs

Review tests when:

* nobody trusts failures
* small changes break many tests
* tests duplicate implementation
* coverage increases but bugs continue

---

# Testing Checklist

Before completion:

[ ] Business rules tested

[ ] Permissions tested

[ ] Failure cases included

[ ] External services mocked

[ ] Tests remain understandable

---

# Final Principle

Good tests give developers confidence to change code.

They protect behavior without blocking improvement.