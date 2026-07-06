# FastAPI Schemas

Schemas define API contracts.

They control what enters and leaves the system.

Schemas protect boundaries.

---

# Schema Philosophy

Schemas exist for:

* validation
* serialization
* documentation
* API stability

They are contracts between backend and clients.

Treat schemas as public interfaces.

---

# Existing Project Rule

Existing schema patterns have priority.

Before changing:

Understand:

* current naming
* validation approach
* Pydantic version
* response format

Do not rewrite schemas unnecessarily.

---

# Schema Location

Standard location:

schemas/

Example:

schemas/

├── user.py

├── product.py

└── order.py

Group schemas by feature.

---

# Separate Database Models And Schemas

Never expose ORM models directly.

Models describe:

Database structure.

Schemas describe:

API contracts.

They have different responsibilities.

---

# Schema Naming

Use clear names.

Preferred:

UserCreate

UserUpdate

UserResponse

UserListResponse

Avoid:

UserSchema

UserModel

UserData

when purpose is unclear.

---

# Request Schemas

Request schemas define incoming data.

Example:

class UserCreate(BaseModel):

```
email: EmailStr

name: str
```

Used for:

POST

PUT

PATCH

---

# Response Schemas

Response schemas define outgoing data.

Example:

class UserResponse(BaseModel):

```
id: int

email: EmailStr

name: str
```

Never accidentally expose sensitive database fields.

---

# Base Schemas

Use base schemas only when they reduce duplication.

Example:

UserBase

UserCreate

UserResponse

Avoid inheritance chains that become confusing.

---

# Validation

Put data validation inside schemas.

Examples:

* email format
* length limits
* allowed values
* field formats

Reject invalid data early.

---

# Business Validation

Do not put business workflows inside schemas.

Bad:

Checking user balance inside schema.

Good:

Checking email format inside schema.

Business rules belong in services.

---

# Pydantic V2 Standard

Use Pydantic v2 style.

Example:

from pydantic import BaseModel, ConfigDict

class UserResponse(BaseModel):

```
id: int

email: str


model_config = ConfigDict(
    from_attributes=True
)
```

---

# OpenAPI Examples

Every important request schema should include examples.

Use:

json_schema_extra

Example:

class UserCreate(BaseModel):

```
email: EmailStr

name: str


model_config = {

    "json_schema_extra": {

        "example": {

            "email": "user@example.com",

            "name": "John"

        }

    }

}
```

Documentation should help API consumers.

---

# Optional Fields

Be explicit.

Example:

class UserUpdate(BaseModel):

```
name: str | None = None
```

Avoid unclear optional behavior.

---

# Defaults

Use defaults carefully.

Defaults should represent real system behavior.

Avoid hiding missing required data.

---

# Sensitive Data

Never expose:

* passwords
* tokens
* secrets
* private fields

in response schemas.

---

# Internal Schemas

Create internal schemas only when needed.

Avoid creating:

UserInternal

UserDatabase

UserSystem

without actual responsibility.

---

# Nested Schemas

Use nested schemas when they improve API clarity.

Avoid returning massive nested objects unnecessarily.

APIs should expose what clients need.

---

# Schema Conversion

Keep conversions predictable.

Flow:

Request Schema

↓

Service

↓

Model

↓

Response Schema

Avoid leaking database objects everywhere.

---

# Field Naming

Use consistent naming.

Prefer API consistency over internal preference.

Avoid randomly mixing:

user_id

userId

---

# Large Schemas

Split schemas when:

* responsibilities differ
* request and response diverge
* security requires separation

Do not split only because fields increase.

---

# Schema Testing

Test:

* validation rules
* required fields
* invalid inputs
* serialization behavior

Schemas protect API contracts.

---

# Schema Warning Signs

Review schemas when:

* ORM models are returned directly
* passwords appear in responses
* business logic exists in validators
* inheritance becomes confusing

---

# Schema Checklist

Before completing:

[ ] Request schemas exist

[ ] Response schemas exist

[ ] Sensitive fields hidden

[ ] Validation belongs here

[ ] Examples added

[ ] API contract is clear

---

# Final Principle

Schemas are promises.

A good schema makes APIs predictable without exposing internal implementation.