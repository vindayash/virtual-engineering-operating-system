# FastAPI Template

FastAPI projects should stay simple, structured and scalable.

Use framework strengths.

Avoid unnecessary layers.

---

# Purpose

Provide a reusable FastAPI structure with:

* versioned APIs
* schemas
* CRUD separation
* optional services
* custom exceptions
* clear configuration

---

# Project Structure

Recommended:

app/

├── api/

│   └── v1/

│       ├── endpoints/

│       └── router.py

│

├── core/

│   ├── config.py

│   ├── security.py

│   └── exceptions.py

│

├── models/

├── schemas/

├── crud/

├── services/

├── db/

├── dependencies/

├── utils/

└── main.py

---

# API Versioning

Use version folders.

Example:

api/v1/

Benefits:

* protects clients
* allows future changes
* maintains compatibility

---

# Router Layer

Routers handle HTTP concerns.

Responsibilities:

* request handling
* dependencies
* response codes

Avoid large business logic here.

---

# Schema Layer

Use Pydantic schemas for:

* request validation
* response contracts
* documentation

---

# Schema Example Pattern

Use:

json_schema_extra

for examples and documentation.

Schemas should explain API usage.

---

# Model Layer

Models represent database structure.

Keep:

database concerns

separate from:

API contracts

---

# CRUD Layer

CRUD handles database operations.

Use for:

* queries
* persistence
* database logic

Example:

create_user()

get_user_by_id()

update_user()

---

# Service Layer

Services are optional.

Use when logic includes:

* workflows
* multiple CRUD operations
* external APIs
* business rules

---

# Avoid Empty Services

Do not create:

Router

↓

Service

↓

CRUD

when service only forwards calls.

Remove unnecessary layers.

---

# Dependency Layer

Use dependencies for:

* authentication
* permissions
* reusable request logic

Keep routes clean.

---

# Custom Exceptions

Create application exceptions.

Examples:

UserNotFoundException

PermissionDeniedException

Benefits:

* consistent errors
* cleaner code
* centralized handling

---

# Exception Handling

Handle errors globally.

Return:

* consistent format
* safe messages
* proper status codes

---

# Configuration

Use centralized config.

Examples:

* environment variables
* application settings

Avoid hardcoded values.

---

# Security

Implement:

* authentication
* authorization
* validation

Follow:

handbook/security/

---

# Database

Use database folder for:

* sessions
* connections
* initialization

Keep database setup isolated.

---

# Background Tasks

Use only when needed.

Examples:

* email sending
* slow operations
* async workflows

---

# Utilities

Utilities should contain reusable helpers.

Avoid:

misc.py

common.py

with unrelated code.

---

# Testing Structure

Recommended:

tests/

├── api/

├── services/

└── database/

Match project needs.

---

# Documentation

Use FastAPI automatic documentation.

Enhance with:

* schemas
* descriptions
* examples

---

# Dependency Rules

Before adding packages:

Check FastAPI ecosystem first.

Avoid unnecessary libraries.

---

# Small Project Rule

Small applications may skip:

* services
* complex folders

Start simple.

Grow naturally.

---

# AI Generation Rule

Claude should:

* follow existing project first
* create only needed layers
* avoid enterprise boilerplate

---

# Avoid

Never automatically add:

* repository pattern
* unnecessary services
* complex inheritance
* unused abstractions

---

# Final Principle

A good FastAPI project is explicit.

Simple endpoints.

Clear contracts.

Organized growth.