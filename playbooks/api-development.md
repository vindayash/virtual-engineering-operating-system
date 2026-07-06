# Playbook: API Development

APIs are contracts between systems.

Design them carefully.

Changing APIs affects users and integrations.

---

# Purpose

Create APIs that are:

* predictable
* secure
* maintainable
* easy to consume

---

# Active Agents

Use:

* Backend Agent
* Security Agent
* Database Agent
* Reviewer Agent

---

# Step 1: Understand Requirement

Before creating endpoints:

Understand:

* user need
* data required
* actions supported
* consumers

Do not design APIs blindly.

---

# Step 2: Review Existing APIs

For existing projects:

Check:

* route patterns
* response formats
* authentication
* naming

Maintain consistency.

---

# Step 3: Design Contract

Define:

* endpoint
* method
* request format
* response format
* errors

API contract comes before implementation.

---

# Endpoint Design

Prefer resource-based design.

Example:

GET /users/{id}

Instead of:

GET /getUserData

---

# API Versioning

Use versioning when compatibility matters.

Example:

/api/v1/

Protect existing consumers.

---

# Step 4: Request Validation

Validate:

* body
* query parameters
* headers
* files

Never trust external input.

---

# Schema Usage

Use framework tools.

Examples:

FastAPI:

Pydantic schemas

Django REST Framework:

Serializers

Keep contracts explicit.

---

# Step 5: Response Design

Return:

* required fields only
* consistent structure
* expected status codes

Avoid exposing internal models directly.

---

# Step 6: Authentication

Decide:

Who is making the request?

Apply authentication when needed.

---

# Step 7: Authorization

Decide:

Can this user perform this action?

Check:

* ownership
* permissions
* roles

---

# Step 8: Business Logic

Place logic appropriately.

Simple:

Route/View

Complex:

Service layer

Do not create unnecessary layers.

---

# Step 9: Database Interaction

Review:

* queries
* transactions
* performance
* relationships

Avoid inefficient access.

---

# Step 10: Error Handling

Create predictable errors.

Avoid exposing:

* stack traces
* internal details

---

# Custom Exceptions

Use custom exceptions when they improve:

* clarity
* consistency
* reuse

---

# Step 11: Documentation

Document APIs when useful.

Include:

* behavior
* parameters
* examples

Avoid documenting obvious implementation.

---

# Step 12: Testing

Test:

* success cases
* validation failures
* permission failures
* edge cases

---

# Performance Review

Before completion check:

* unnecessary queries
* large responses
* expensive operations

---

# Security Review

Verify:

[ ] Input validated

[ ] Authentication applied

[ ] Authorization checked

[ ] Sensitive data hidden

---

# API Change Rule

For existing APIs:

Do not break contracts without planning.

Consider:

* clients
* migrations
* versions

---

# AI Behavior Rule

Claude must:

* follow existing API patterns
* create minimal required changes
* avoid unnecessary abstractions

---

# Avoid

Do not automatically:

* create service layers everywhere
* expose database models
* ignore permissions
* add new libraries

---

# Completion Checklist

Before finishing:

[ ] Contract clear

[ ] Validation exists

[ ] Errors handled

[ ] Security checked

[ ] Tests considered

---

# Final Principle

A good API is boring.

Predictable.

Reliable.

Easy to trust.