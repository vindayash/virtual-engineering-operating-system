# Flask Request Handling

Request handlers connect external clients with application behavior.

They are entry points.

They should not contain the entire system.

---

# Request Handling Philosophy

Routes should answer:

"How does the client interact with the application?"

They should not contain all details of:

"How does the business process work?"

Keep responsibilities separated.

---

# Existing Project Rule

Existing request patterns have priority.

Before changing:

Understand:

* route organization
* validation style
* response format
* error handling

Do not rewrite handlers unnecessarily.

---

# Route Responsibility

Routes handle:

* HTTP requests
* input collection
* authentication checks
* calling application logic
* responses

Keep routes understandable.

---

# Simple Application Flow

For simple CRUD:

Route

↓

Model

is acceptable.

Do not add unnecessary layers.

---

# Complex Application Flow

For business workflows:

Route

↓

Service

↓

Database

Use when complexity exists.

---

# Service Layer Rule

Services are optional.

Use services for:

* multi-step operations
* business rules
* transactions
* external integrations

Avoid empty forwarding services.

---

# Avoid Fat Routes

Avoid routes containing:

* payment processing
* large calculations
* email workflows
* complex database operations

Move responsibility when needed.

---

# Request Validation

Validate incoming data.

Check:

* required fields
* types
* formats
* constraints

Never trust client input.

---

# Validation Location

Simple validation:

request layer

Complex business validation:

service layer

Keep ownership clear.

---

# Request Parsing

Avoid manually parsing everything repeatedly.

Use consistent patterns.

Examples:

* schemas
* validators
* request helpers

depending on project size.

---

# Response Format

Responses should be consistent.

Example:

{
"data": {},
"message": ""
}

Follow existing project conventions.

---

# Status Codes

Return meaningful HTTP status codes.

Examples:

201 Created

400 Bad Request

404 Not Found

Avoid returning 200 for everything.

---

# Error Handling

Do not hide errors.

Avoid:

try:

```
everything()
```

except:

```
pass
```

Failures should be visible.

---

# Custom Exceptions

Prefer application exceptions.

Example:

Service raises:

UserNotFound

Handler converts:

HTTP response

Keep Flask separate from business logic.

---

# Authentication

Routes should clearly show authentication requirements.

Avoid hidden security behavior.

---

# Authorization

Always verify:

* permissions
* ownership
* access rules

Login alone is not enough.

---

# External Services

Avoid calling external systems directly from routes.

Prefer:

Route

↓

Service

↓

Integration

---

# File Uploads

Validate:

* size
* type
* permissions

Never trust uploaded files.

---

# Pagination

Large lists should support pagination.

Avoid unlimited responses.

---

# Filtering

Validate query parameters.

Avoid unsafe direct database filtering.

---

# Logging

Log important request failures.

Avoid logging:

* passwords
* tokens
* sensitive data

---

# Testing Routes

Test:

* request behavior
* responses
* validation
* authentication
* permissions

Routes define external contracts.

---

# Warning Signs

Review routes when:

* route files become huge
* database logic exists everywhere
* business rules are duplicated
* external APIs are called directly

---

# Request Checklist

Before completion:

[ ] Input validated

[ ] Response consistent

[ ] Permissions checked

[ ] Business logic separated when needed

[ ] Errors handled safely

---

# Final Principle

Routes should direct traffic.

They should not become the destination.