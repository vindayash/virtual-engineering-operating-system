# FastAPI Exception Handling

Exceptions define how application failures become API responses.

Good exception handling creates predictable failures.

---

# Exception Philosophy

Errors should be:

* consistent
* understandable
* secure
* easy to debug

Failures are part of system design.

---

# Existing Project Rule

Existing exception handling has priority.

Before changing:

Understand:

* current error format
* exception hierarchy
* logging approach

Do not introduce a new system without migration.

---

# Exception Responsibility

Separate:

Application Error

from

HTTP Response

Business code should not depend on FastAPI.

---

# Standard Structure

Recommended:

core/

├── exceptions.py

└── exception_handlers.py

---

# Exception Flow

Preferred:

Service

↓

Custom Exception

↓

Exception Handler

↓

JSON Response

---

# Avoid HTTPException In Services

Bad:

services/user.py

raise HTTPException(
status_code=404,
detail="User not found"
)

This couples business logic with FastAPI.

---

# Preferred Service Pattern

services/user.py

raise UserNotFound()

The service only explains:

what failed.

Not:

how HTTP should respond.

---

# Custom Exceptions

Example:

class AppException(Exception):

```
message = "Application error"

status_code = 400
```

class UserNotFound(AppException):

```
message = "User not found"

status_code = 404
```

Application failures become reusable.

---

# Exception Handlers

Handlers convert exceptions.

Example:

@app.exception_handler(AppException)

async def app_exception_handler(
request,
exc
):

```
return JSONResponse(
    status_code=exc.status_code,
    content={
        "error": exc.message
    }
)
```

---

# Error Response Format

Keep responses consistent.

Example:

{
"success": false,
"error": {
"code": "USER_NOT_FOUND",
"message": "User not found"
}
}

Clients should receive predictable errors.

---

# HTTPException Usage

HTTPException is acceptable inside:

api/v1/endpoints/

For:

* request-specific HTTP behavior
* simple route failures

Avoid spreading it everywhere.

---

# Validation Errors

Handle validation errors consistently.

FastAPI validation failures should return:

* clear messages
* safe information
* useful field details

---

# Unexpected Exceptions

Unexpected failures should:

* be logged
* return safe responses
* hide internals

Never expose:

* stack traces
* database errors
* secrets

---

# Logging Exceptions

Log:

* exception type
* operation context
* debugging information

Never log:

* passwords
* tokens
* private data

---

# External Service Errors

Convert external failures.

Example:

Payment provider timeout

↓

PaymentServiceUnavailable

Do not leak third-party errors directly.

---

# Database Exceptions

Avoid exposing database errors.

Convert:

IntegrityError

↓

Meaningful application exception

Example:

Duplicate email

↓

UserAlreadyExists

---

# Exception Naming

Use meaningful names.

Good:

InvalidOrderState

PaymentFailed

UserNotFound

Bad:

CustomError

GeneralException

---

# Do Not Catch Everything

Avoid:

try:

```
operation()
```

except Exception:

```
pass
```

Silent failures create production issues.

---

# Testing Exceptions

Test:

* custom exceptions
* handler responses
* status codes
* error formats

Errors are part of API contracts.

---

# Warning Signs

Review when:

* HTTPException exists everywhere
* services import FastAPI
* error responses are inconsistent
* stack traces reach clients
* failures disappear

---

# Exception Checklist

Before completion:

[ ] Services use custom exceptions

[ ] Responses are consistent

[ ] Errors are logged safely

[ ] Internals are hidden

[ ] Unexpected failures handled

---

# Final Principle

Services decide what failed.

Exception handlers decide how clients see the failure.

Keep these responsibilities separate.