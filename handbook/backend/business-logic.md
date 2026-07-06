# Business Logic

Business logic represents the rules and behavior that make an application valuable.

Protecting business logic is the main responsibility of backend engineering.

---

# Business Logic Philosophy

Business logic should be:

* clear
* explicit
* testable
* maintainable

Business rules should be easy to find.

Important behavior should never be hidden.

---

# Understand The Business First

Before implementing logic:

Understand:

* why the rule exists
* who depends on it
* what happens when it changes
* failure scenarios

Code follows understanding.

---

# Existing System Rule

Existing business logic organization has priority.

Before moving logic:

Understand:

* current patterns
* dependencies
* historical reasons

Do not relocate business rules only because another structure looks cleaner.

Improve gradually.

---

# Keep Business Rules Visible

Important decisions should be obvious.

Good:

if user.balance < order.total:
reject_order()

The rule is visible.

Bad:

magic_validator.process(user, order)

where behavior is hidden.

---

# Separate Transport From Business

Business logic should not depend on:

* HTTP requests
* API responses
* route handlers
* controllers

The business rule should work regardless of how it is triggered.

---

# API Layer Responsibility

API layers should handle:

* request parsing
* authentication checks
* validation
* response formatting

Avoid placing complex workflows directly inside APIs.

---

# Business Layer Responsibility

Business layers handle:

* decisions
* workflows
* rules
* coordination

Example:

Order processing:

* check inventory
* calculate pricing
* create order
* trigger payment

---

# Database Is Not Business Logic

Databases store and retrieve data.

Avoid hiding business workflows inside:

* queries
* ORM tricks
* database-specific behavior

Some constraints belong in databases.

Business decisions should remain understandable.

---

# Avoid Anemic Forwarding

Do not create fake business layers.

Bad flow:

Controller

↓

Service

↓

Manager

↓

Repository

where each layer only forwards the request.

Every layer needs responsibility.

---

# Rules Should Have Names

Complex business conditions should communicate meaning.

Avoid:

if status == 3 and count > 5 and active:

Prefer:

if user_can_receive_reward():

Meaning matters.

---

# Handle Edge Cases Explicitly

Business logic should define:

* allowed states
* invalid actions
* failure behavior

Avoid assuming perfect workflows.

---

# State Changes

State transitions should be controlled.

Example:

Order:

Pending

↓

Paid

↓

Shipped

Prevent invalid transitions.

Example:

Cancelled

↓

Shipped

should not happen.

---

# External Dependencies

Business rules should not blindly trust external services.

Always handle:

* failures
* delays
* unexpected responses

External systems are unreliable.

---

# Duplication vs Abstraction

Small duplication can be acceptable.

Create abstractions only when:

* patterns are understood
* duplication creates problems
* meaning is clear

Wrong abstractions hide business behavior.

---

# Testing Business Logic

Business logic deserves strong tests.

Prioritize:

* important rules
* edge cases
* state changes
* failures

Business failures are expensive failures.

---

# Changing Business Rules

Before changing rules:

Check:

* existing behavior
* affected users
* dependent systems
* backward compatibility

Small changes can have large impact.

---

# Documentation

Document business rules when:

* reasoning is not obvious
* regulations affect behavior
* unusual decisions exist

Explain why.

Not what.

---

# Warning Signs

Review business logic when:

* nobody knows where rules exist
* APIs contain large workflows
* behavior is duplicated everywhere
* changes break unrelated features

---

# Business Logic Checklist

Before completing:

[ ] Rule is understandable

[ ] Correct layer owns behavior

[ ] Edge cases considered

[ ] Failures handled

[ ] Tests protect important cases

---

# Final Principle

Business logic is the heart of the system.

Make it easy to find, understand and safely change.