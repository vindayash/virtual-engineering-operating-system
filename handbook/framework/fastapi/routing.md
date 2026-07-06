# FastAPI Routing

Routing defines how external requests enter the application.

Routes should be thin.

Business decisions belong outside endpoints.

---

# Routing Philosophy

FastAPI endpoints should answer:

"How does the client communicate with the system?"

They should not answer:

"How does the business process work?"

Keep HTTP handling separate from application behavior.

---

# Existing Project Rule

Existing routing patterns have priority.

Before changing routes:

Understand:

* current API structure
* versioning approach
* naming conventions
* response patterns

Do not reorganize routes unnecessarily.

---

# API Version Structure

For new production APIs use versioning.

Standard:

api/

└── v1/

```
├── router.py

└── endpoints/

    ├── users.py

    ├── auth.py

    └── orders.py
```

---

# Main Application Router

main.py should only register application-level configuration.

Example:

app.include_router(
api_router,
prefix="/api/v1"
)

Avoid defining endpoints directly inside main.py.

---

# Version Router

api/v1/router.py combines feature routers.

Example:

api_router.include_router(
users.router,
prefix="/users",
tags=["Users"]
)

Each feature manages its own routes.

---

# Endpoint Responsibility

Endpoints handle:

* request receiving
* dependency injection
* authentication dependencies
* permission checks
* response models
* status codes

Keep endpoints small.

---

# Endpoint Should Not Handle

Avoid:

* complex business workflows
* database queries
* external API calls
* large calculations

Move those responsibilities.

---

# Request Flow

Preferred:

Endpoint

↓

Service (if business logic exists)

↓

CRUD

↓

Database

For simple operations:

Endpoint

↓

CRUD

Service is optional.

---

# Service Usage Rule

Use services when:

* multiple operations happen
* business decisions exist
* external systems are involved
* workflows need coordination

Do not create services that only forward CRUD calls.

---

# CRUD Usage Rule

CRUD handles:

* queries
* database changes
* persistence logic

Endpoints may call CRUD directly for simple data operations.

Example:

GET /countries

does not need:

CountryService.get_all()

calling:

CountryCRUD.get_all()

---

# Route Naming

Use resource-based naming.

Good:

GET /users

POST /users

GET /users/{user_id}

Avoid:

GET /getUsers

POST /createUser

---

# Action Routes

Use actions only when they represent operations.

Good:

POST /orders/{id}/cancel

because cancellation is a business action.

---

# Dependency Injection

Use FastAPI Depends for:

* database sessions
* authentication
* reusable request dependencies

Avoid hiding business logic inside dependencies.

---

# Response Models

Always define response contracts.

Example:

@router.get(
"/{id}",
response_model=UserResponse
)

Do not expose database models directly.

---

# Status Codes

Declare expected status codes.

Example:

@router.post(
"/",
status_code=201
)

Responses should be predictable.

---

# Authentication In Routes

Routes should declare access requirements.

Example:

current_user = Depends(get_current_user)

Authentication should be visible.

---

# Authorization

Routes may trigger permission checks.

But complex authorization rules belong in business logic.

Example:

Can user update this resource?

belongs closer to the workflow.

---

# Error Handling

Avoid spreading HTTPException everywhere.

Preferred:

Service raises:

UserNotFound()

Exception handler converts:

↓

HTTP 404 response

Keep business errors framework independent.

---

# Pagination

List endpoints should consider pagination.

Avoid returning unlimited datasets.

Support:

* limit
* offset
* cursor

depending on requirements.

---

# Filtering

Validate filters.

Avoid directly converting all query parameters into database queries.

Input controls data access.

---

# Route File Size

Split routes when responsibility grows.

Not because line count increases.

Split by feature ownership.

---

# Routing Warning Signs

Review routing when:

* endpoints contain hundreds of lines
* SQL queries exist in routes
* business workflows exist in routes
* routes call many unrelated systems

---

# Routing Checklist

Before completing:

[ ] Route responsibility is clear

[ ] Business logic is separated

[ ] Response model exists

[ ] Authentication is clear

[ ] Errors are handled properly

[ ] Versioning is respected

---

# Final Principle

FastAPI routes are entry points.

They should connect the outside world to your application.

They should not become the application.