# FastAPI Project Structure

FastAPI projects should be simple, explicit and production friendly.

Structure exists to separate responsibilities.

Not to create unnecessary layers.

---

# Project Philosophy

FastAPI architecture should make it clear:

* where requests enter
* where business decisions happen
* where database operations happen
* where external integrations exist

Every folder must have ownership.

---

# Existing Project Rule

Existing FastAPI projects have priority.

Before modifying structure:

Understand:

* current architecture
* folder organization
* patterns
* team decisions

Do not migrate a working project to this structure only because it looks cleaner.

Existing consistency wins.

---

# New Project Standard

For new FastAPI projects, prefer:

app/

├── main.py

│

├── api/

│   ├── deps.py

│   └── v1/

│       ├── router.py

│       └── endpoints/

│           ├── users.py

│           └── auth.py

│

├── core/

│   ├── config.py

│   ├── security.py

│   ├── logging.py

│   └── exceptions.py

│


├── database/

│   ├── base.py

│   ├── session.py

│   └── migrations/

│

├── models/

│   └── user.py

│

├── schemas/

│   └── user.py

│

├── crud/

│   └── user.py

│

├── services/

│   └── user.py

│

├── integrations/

│   └── external_service.py

│

├── middleware/

│   └── request_logging.py

│

├── utils/

│   └── specific_helpers.py

│

└── tests/

---

# Custom Exceptions

Location:

core/exceptions.py

Custom exceptions represent application failures.

They keep business logic independent from FastAPI.

---

# Exception Flow

Preferred flow:

Service

↓

Application Exception

↓

Exception Handler

↓

HTTP Response

---

# Do Not Raise HTTPException Everywhere

Avoid:

raising HTTPException inside:

* services
* crud
* integrations
* business logic

Bad:

from fastapi import HTTPException

def create_user():

```
if exists:

    raise HTTPException(
        status_code=400,
        detail="User exists"
    )
```

This couples business rules with the API framework.

---

# Preferred Approach

Service:

raise UserAlreadyExists()

Exception:

class UserAlreadyExists(AppException):

```
message = "User already exists"

status_code = 400
```

Handler converts it:

UserAlreadyExists

↓

JSON Response

---

# Where HTTPException Is Acceptable

HTTPException is acceptable inside:

api/v1/endpoints/

Examples:

* request-specific failures
* HTTP-only behavior

Application logic should use application exceptions.

---

# Exception Benefits

Custom exceptions provide:

* consistent errors
* reusable business failures
* cleaner services
* easier testing

Business logic should work without knowing FastAPI exists.

---

# Exception Organization

Example:

core/

├── exceptions.py

└── exception_handlers.py

Keep exception handling centralized.

---

# Exception Rule

Services decide:

"What went wrong?"

Handlers decide:

"How should HTTP represent it?"

Keep responsibilities separate.


# Request Flow

Standard flow:

Request

↓

Endpoint

↓

Service (when needed)

↓

CRUD

↓

Model

↓

Database

---

# Endpoint Layer

Location:

api/v1/endpoints/

Equivalent to:

Django views.py

or

Controller layer

Responsibilities:

* HTTP handling
* request receiving
* dependency injection
* authentication checks
* response formatting

Endpoints should not contain complex business workflows.

---

# Service Layer

Location:

services/

Services contain business logic.

Examples:

* user registration flow
* payment processing
* order creation
* report generation

Services coordinate actions.

---

# Service Layer Is Optional

Do not create services automatically.

Simple operations can directly use CRUD.

Acceptable:

Endpoint

↓

CRUD

Example:

Fetching countries.

Fetching static records.

Simple lookups.

---

# When To Add Services

Add service layer when logic contains:

* multiple steps
* business rules
* multiple CRUD operations
* transactions
* external integrations

Example:

Create Order:

1. Check inventory

2. Create order

3. Process payment

4. Send notification

This belongs in service.

---

# Avoid Empty Services

Bad:

Endpoint

↓

UserService.get_user()

↓

UserCRUD.get_user()

where service only forwards the call.

This adds files without value.

---

# CRUD Layer

Location:

crud/

CRUD handles database operations.

Responsibilities:

* create queries
* update records
* delete records
* fetch data

CRUD should not contain business decisions.

---

# Models Layer

Location:

models/

Models represent database structure.

Responsible for:

* tables
* relationships
* database fields

Models are not API contracts.

---

# Schemas Layer

Location:

schemas/

Schemas handle:

* request validation
* response contracts
* serialization

Use Pydantic models.

Do not expose ORM models directly.

---

# Schema Standards

Prefer clear request/response schemas.

Example:

UserCreate

UserUpdate

UserResponse

Include OpenAPI examples.

Example:

model_config = {
"json_schema_extra": {
"example": {
"email": "[user@example.com](mailto:user@example.com)",
"name": "John"
}
}
}

---

# API Versioning

Use API versioning for production APIs.

Standard:

api/

└── v1/

```
├── router.py

└── endpoints/
```

Version APIs when contracts need stability.

---

# Router Organization

Each feature owns routes.

Example:

endpoints/

├── users.py

├── products.py

└── orders.py

Combine routers inside:

api/v1/router.py

---

# Core Layer

Location:

core/

Contains:

* settings
* security helpers
* application configuration
* common exceptions

Avoid mixing business logic here.

---

# Database Layer

Location:

database/

Contains:

* engine setup
* sessions
* migrations
* database configuration

Keep database setup centralized.

---

# Integration Layer

Location:

integrations/

Used for:

* third party APIs
* external services
* cloud services

External failures should be handled properly.

---

# Middleware Layer

Location:

middleware/

Used for:

* request logging
* tracing
* security headers
* cross-cutting behavior

Avoid business logic in middleware.

---

# Utils Rule

Avoid dumping everything into utils.

Bad:

utils/helper.py

Prefer:

utils/date_formatter.py

utils/file_validator.py

Purpose should be obvious.

---

# Architecture Growth Rule

Start simple.

Small feature:

Endpoint

↓

CRUD

Growing feature:

Endpoint

↓

Service

↓

CRUD

Do not add layers before they provide value.

---

# Review Checklist

Before adding files/folders:

[ ] Does responsibility exist?

[ ] Is service layer actually needed?

[ ] Is business logic separated?

[ ] Are database operations isolated?

[ ] Is existing project style respected?

---

# Final Principle

A good FastAPI structure should make simple things simple and complex things manageable.

Never create architecture that only moves code through empty layers.