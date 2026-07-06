# FastAPI Example

Reference example for building FastAPI applications using VEOS principles.

Simple first.

Grow when required.

---

# Goal

Create FastAPI projects that are:

* structured
* secure
* maintainable
* easy to understand

---

# Recommended Structure

Example:

app/

├── api/

│   └── v1/

│       ├── endpoints/

│       │   └── users.py

│       └── router.py

│

├── core/

│   ├── config.py

│   ├── security.py

│   └── exceptions.py

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

│

├── db/

│   └── session.py

│

└── main.py

---

# Router Example Responsibility

Router should handle:

* request
* dependencies
* response

Example flow:

Request

↓

Router

↓

CRUD / Service

↓

Database

---

# Schema Example

Schemas define contracts.

Example:

UserCreate

Purpose:

Incoming user creation data.

UserResponse

Purpose:

Outgoing API response.

Do not expose database models directly.

---

# json_schema_extra Usage

Use examples for API documentation.

Good:

Show realistic request examples.

Avoid:

Adding meaningless documentation.

---

# CRUD Example

CRUD handles database operations.

Example:

User CRUD:

* create user
* get user
* update user

Keep database logic reusable.

---

# Service Example

Use service when workflow exists.

Good:

Create order:

1. Validate inventory

2. Create order

3. Process payment

4. Send notification

Service adds value.

---

# Unnecessary Service Example

Avoid:

Endpoint

↓

UserService

↓

create_user()

↓

CRUD

when service adds no logic.

---

# Custom Exception Example

Use:

UserNotFoundException

instead of:

generic Exception

Benefits:

* clearer errors
* consistent responses

---

# Dependency Example

Use dependencies for:

* current user
* permissions
* reusable request behavior

---

# Configuration Example

Good:

Settings loaded from environment.

Bad:

Database password inside code.

---

# Security Example

Endpoint checklist:

Authentication?

Authorization?

Input validation?

Sensitive data hidden?

---

# Small Project Example

Small applications can start with:

routers

schemas

models

Add layers when needed.

---

# Growth Example

Add services when:

business complexity increases.

Add workers when:

background processing required.

Add cache when:

measured performance problem exists.

---

# Avoid Example

Do not create:

app/

├── factories/

├── managers/

├── handlers/

├── processors/

├── services/

├── repositories/

before needing them.

---

# Final Principle

A good FastAPI project grows naturally.

Do not start with the complexity of a company you have not become yet.