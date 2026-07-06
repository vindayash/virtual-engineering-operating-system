# FastAPI Middleware

Middleware handles behavior that applies across requests.

Middleware should manage cross-cutting concerns.

It should not contain business logic.

---

# Middleware Philosophy

Middleware exists for:

* request processing
* response processing
* application-wide behavior

It wraps requests.

It should not control application workflows.

---

# Existing Project Rule

Existing middleware patterns have priority.

Before modifying:

Understand:

* current middleware order
* request lifecycle
* security behavior

Do not replace middleware unnecessarily.

---

# Middleware Location

Standard location:

middleware/

Example:

middleware/

├── request_logging.py

├── security.py

└── timing.py

Each middleware should have a clear purpose.

---

# Good Middleware Usage

Use middleware for:

* request logging
* response timing
* security headers
* CORS handling
* request tracing
* correlation IDs

These affect all requests.

---

# Avoid Business Logic

Never place business workflows in middleware.

Bad:

* creating orders
* processing payments
* changing business state

Middleware should not replace services.

---

# Request Lifecycle

Flow:

Request

↓

Middleware

↓

Endpoint

↓

Service

↓

Response

↓

Middleware

Middleware surrounds execution.

---

# Logging Middleware

Good logging middleware captures:

* request path
* method
* response status
* execution time
* request ID

Avoid logging:

* passwords
* tokens
* sensitive payloads

---

# Request IDs

Use request identifiers when needed.

They help trace:

* errors
* logs
* distributed calls

Useful in production debugging.

---

# Security Middleware

Middleware can enforce:

* security headers
* trusted hosts
* HTTPS behavior
* CORS policy

Security should be consistent.

---

# CORS

Configure CORS intentionally.

Avoid:

allow_origins=["*"]

in production without understanding risk.

Only allow required origins.

---

# Error Middleware

Global error handling may use middleware.

But prefer FastAPI exception handlers for application exceptions.

Keep responsibilities clear.

---

# Performance Middleware

Middleware runs on every request.

Keep it:

* lightweight
* efficient
* necessary

Expensive middleware affects the whole system.

---

# Database In Middleware

Avoid database operations inside middleware unless required.

Database access belongs closer to application logic.

---

# External Calls

Avoid calling external services from middleware.

Failures can affect every endpoint.

---

# Middleware Ordering

Order matters.

Understand execution order before adding middleware.

Incorrect ordering creates hidden bugs.

---

# State Management

Be careful with shared state.

Middleware should avoid:

* global mutable state
* request data leaks
* unsafe caching

---

# Testing Middleware

Test:

* request modifications
* headers
* error behavior
* security behavior

Middleware affects the entire application.

---

# Middleware Warning Signs

Review middleware when:

* business logic exists inside it
* every request becomes slower
* debugging requires tracing hidden behavior
* middleware modifies unexpected data

---

# Middleware Checklist

Before adding middleware:

[ ] Does this apply globally?

[ ] Is this cross-cutting behavior?

[ ] Is it lightweight?

[ ] Does it avoid business logic?

[ ] Are security concerns handled?

---

# Final Principle

Middleware should support the application.

It should not become the application.