# FastAPI SQLAlchemy

SQLAlchemy manages database communication.

Database code should be predictable, isolated and safe.

---

# SQLAlchemy Philosophy

The database layer should answer:

"How is data stored and retrieved?"

It should not answer:

"What should the business do?"

Separate persistence from decisions.

---

# Existing Project Rule

Existing database patterns have priority.

Before changing:

Understand:

* SQLAlchemy version
* session handling
* model patterns
* migration strategy

Do not rewrite database architecture unnecessarily.

---

# Standard Structure

Recommended:

database/

├── base.py

├── session.py

└── migrations/

models/

├── user.py

crud/

├── user.py

services/

├── user.py

---

# Responsibility Flow

Preferred:

Endpoint

↓

Service (when needed)

↓

CRUD

↓

Model

↓

Database

Simple operations:

Endpoint

↓

CRUD

Service is optional.

---

# Models Responsibility

Models define database structure.

Examples:

* tables
* columns
* relationships
* constraints

Models should not contain API behavior.

---

# Model Example

class User(Base):

```
__tablename__ = "users"


id = Column(
    Integer,
    primary_key=True
)


email = Column(
    String,
    unique=True
)
```

---

# Keep Models Focused

Avoid putting:

* request validation
* API formatting
* business workflows

inside models.

---

# CRUD Responsibility

CRUD handles persistence.

Responsibilities:

* create records
* fetch records
* update records
* delete records
* database queries

CRUD should not contain business decisions.

---

# CRUD Example

def get_user_by_email(
db,
email
):

```
return (
    db.query(User)
    .filter(User.email == email)
    .first()
)
```

---

# Service Responsibility

Services coordinate workflows.

Example:

Register user:

Service:

* check existing user
* apply business rules
* call CRUD create
* trigger notification

CRUD:

* insert user

---

# Avoid Fat CRUD

Bad:

crud/order.py

* calculate discounts
* process payments
* send emails
* update inventory

These are business workflows.

Move them to services.

---

# Avoid Empty Services

Do not create:

Service

↓

CRUD

when service adds no logic.

Simple CRUD access is acceptable.

---

# Session Management

Database sessions should be handled through dependencies.

Example:

db = Depends(get_db)

Avoid manually creating sessions everywhere.

---

# Transactions

Transactions protect consistency.

Use when multiple database changes must succeed together.

Example:

Create order

*

Reduce inventory

Both succeed.

Or both fail.

---

# Commit Responsibility

Keep commits predictable.

Avoid random commits throughout the codebase.

Understand transaction boundaries.

---

# Queries

Queries should be:

* understandable
* efficient
* intentional

Avoid:

* hidden expensive queries
* unnecessary database calls
* loading unused data

---

# Relationships

Use relationships carefully.

Consider:

* query behavior
* loading strategy
* performance impact

Avoid accidental large queries.

---

# Migrations

Database changes should use migrations.

Never manually change production schemas.

Migrations provide:

* history
* repeatability
* safer deployment

---

# Constraints

Protect data integrity using:

* unique constraints
* foreign keys
* nullable rules

The database should protect important rules.

---

# Indexing

Add indexes based on:

* query patterns
* performance needs
* measurements

Do not index everything.

Indexes have cost.

---

# Raw SQL

Raw SQL is acceptable when:

* ORM becomes inefficient
* queries need optimization
* database features are required

Use intentionally.

---

# Security

Prevent:

* SQL injection
* unsafe queries
* exposed credentials

Use parameterized queries.

---

# Performance

Before optimization:

Measure.

Find slow queries.

Improve targeted areas.

Avoid guessing.

---

# Testing Database Code

Test:

* important queries
* transactions
* constraints
* failure scenarios

Data correctness matters.

---

# Warning Signs

Review database code when:

* business logic exists in CRUD
* queries are duplicated everywhere
* sessions are manually created everywhere
* models control API behavior
* commits happen unpredictably

---

# SQLAlchemy Checklist

Before completion:

[ ] Models represent database only

[ ] CRUD handles persistence

[ ] Services own workflows

[ ] Sessions managed correctly

[ ] Transactions are safe

[ ] Migrations included

---

# Final Principle

The database stores truth.

Keep data access clear, predictable and separate from business decisions.