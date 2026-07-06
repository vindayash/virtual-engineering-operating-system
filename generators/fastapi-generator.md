# FastAPI Generator

Generate FastAPI applications using VEOS standards.

Create only what the project needs.

Avoid unnecessary complexity.

---

# Purpose

Guide generation of:

* FastAPI projects
* modules
* APIs
* backend components

following consistent architecture.

---

# Required References

Follow:

templates/fastapi-template.md

handbook/backend/

handbook/framework/

handbook/security/

---

# Generation Rule

Before generating:

Understand:

* project size
* requirements
* database needs
* authentication needs

Do not generate everything by default.

---

# Step 1: Determine Project Size

Small project:

Use:

* routers
* schemas
* models

Medium project:

Add:

* crud
* services when useful
* dependencies

Large project:

Add:

* stronger boundaries
* background processing
* infrastructure support

---

# Step 2: Create Base Structure

Default:

app/

api/

core/

models/

schemas/

crud/

db/

Optional:

services/

workers/

integrations/

Add only when needed.

---

# Step 3: Generate Configuration

Create:

core/config.py

Handle:

* environment variables
* settings
* application configuration

No hardcoded secrets.

---

# Step 4: Generate API Layer

Create:

api/v1/

Include:

* routers
* endpoints
* dependencies

Use versioning when appropriate.

---

# Step 5: Generate Schemas

Create schemas for:

Requests

Responses

Use Pydantic.

Include:

json_schema_extra

when documentation benefits.

---

# Step 6: Generate Models

Models should represent:

database structure

Do not mix with:

API responses

---

# Step 7: Generate CRUD

Create CRUD when database operations need separation.

Responsibilities:

* queries
* persistence
* database operations

---

# Step 8: Generate Services

Services are optional.

Generate only for:

* business workflows
* multiple operations
* external integrations

---

# Avoid Empty Services

Do not generate:

Endpoint

↓

Service

↓

CRUD

unless service adds logic.

---

# Step 9: Generate Exceptions

Create:

core/exceptions.py

Use:

* custom exceptions
* centralized handling
* consistent responses

---

# Step 10: Generate Security

When required:

Add:

* authentication
* authorization
* dependencies

Follow security handbook.

---

# Step 11: Generate Tests

Prioritize:

* API behavior
* business logic
* permissions

Avoid meaningless tests.

---

# Dependency Rules

Before adding packages:

Check:

Can FastAPI already solve this?

---

# AI Generation Rule

Claude must:

* generate minimal required files
* explain structure choices
* avoid unused folders

---

# Never Generate Automatically

Avoid:

* repository pattern everywhere
* excessive inheritance
* unused services
* unnecessary abstractions

---

# Output Format

Return:

## Structure

Generated files.

## Reasoning

Why structure fits.

## Code

Implementation.

## Next Steps

Only required improvements.

---

# Final Principle

Generate the project needed today.

Leave room for tomorrow.