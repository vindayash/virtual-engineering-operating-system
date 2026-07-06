# FastAPI Dependencies

Dependencies provide reusable request-level behavior.

They should simplify request handling.

They should not hide application logic.

---

# Dependency Philosophy

FastAPI dependencies exist for:

* shared request requirements
* resource management
* authentication loading
* common validation

Dependencies prepare execution.

They should not become the execution.

---

# Existing Project Rule

Existing dependency patterns have priority.

Before changing:

Understand:

* current dependency structure
* authentication flow
* database handling
* project conventions

Do not rewrite dependencies unnecessarily.

---

# Dependency Location

Common dependencies live in:

api/deps.py

Example:

api/

├── deps.py

└── v1/

```
└── endpoints/
```

Keep reusable API dependencies centralized.

---

# Good Dependency Usage

Use dependencies for:

* database sessions
* current user loading
* permission checks
* request context
* shared parameters

Example:

db: Session = Depends(get_db)

---

# Database Dependencies

Database sessions should be managed consistently.

Example:

def get_db():

```
db = SessionLocal()

try:

    yield db

finally:

    db.close()
```

Resource cleanup matters.

---

# Authentication Dependencies

Authentication belongs in dependencies.

Example:

current_user = Depends(
get_current_user
)

Routes should clearly show authentication requirements.

---

# Authorization Dependencies

Simple authorization can exist in dependencies.

Example:

Require admin user.

Complex business permissions belong closer to business logic.

---

# Avoid Business Logic In Dependencies

Bad:

Depends(process_payment)

Bad:

Depends(create_order)

Dependencies should not execute workflows.

---

# Request Flow

Correct:

Endpoint

↓

Dependency loads resources

↓

Service executes workflow

Avoid:

Dependency executes workflow

↓

Endpoint returns result

---

# Dependency Size

Dependencies should stay focused.

Good:

get_current_user()

Bad:

prepare_everything()

Large dependencies hide behavior.

---

# Dependency Chains

Avoid deep dependency chains.

Example:

Dependency A

↓

Dependency B

↓

Dependency C

Hard-to-follow dependencies create debugging problems.

---

# External Services

Dependencies may provide clients.

Example:

def get_email_client():

```
return EmailClient()
```

But business actions stay in services.

---

# Configuration Dependencies

Use dependencies when request-specific configuration is needed.

Application configuration should usually come from settings.

---

# Caching Dependencies

Use dependency caching intentionally.

Understand:

* lifecycle
* request scope
* object reuse

Avoid unexpected shared state.

---

# Testing Benefits

Good dependencies make testing easier.

Allow overriding:

* database sessions
* users
* external clients

during tests.

---

# Dependency Overrides

Use:

app.dependency_overrides

for testing.

Avoid changing production code for tests.

---

# Security

Dependencies handling security must:

* validate inputs
* fail safely
* avoid leaking information

Authentication dependencies protect entry points.

---

# Common Mistakes

Avoid:

* putting CRUD operations in dependencies
* hiding workflows
* creating huge dependency trees
* replacing services with dependencies

---

# Dependency Review Checklist

Before creating:

[ ] Is this request-level behavior?

[ ] Is it reused?

[ ] Does it avoid business logic?

[ ] Is lifecycle managed?

[ ] Is it easy to test?

---

# Final Principle

Dependencies should prepare what an endpoint needs.

They should not secretly perform what the endpoint does.