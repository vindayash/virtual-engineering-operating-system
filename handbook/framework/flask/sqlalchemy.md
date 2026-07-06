# Flask SQLAlchemy

SQLAlchemy manages database communication in Flask applications.

Database access should be clear, predictable and safe.

---

# SQLAlchemy Philosophy

Database code should answer:

"How is data stored and retrieved?"

Business logic should answer:

"What should happen?"

Keep these responsibilities separate.

---

# Existing Project Rule

Existing database patterns have priority.

Before changing:

Understand:

* ORM usage
* session handling
* migrations
* query organization

Do not rewrite database architecture unnecessarily.

---

# Extension Setup

Prefer centralized initialization.

Example:

extensions.py

db = SQLAlchemy()

Application factory:

db.init_app(app)

Avoid scattered database setup.

---

# Model Responsibility

Models define:

* tables
* fields
* relationships
* constraints

Models represent data.

---

# Model Example

class User(db.Model):

```
id = db.Column(
    db.Integer,
    primary_key=True
)


email = db.Column(
    db.String,
    unique=True
)
```

---

# Avoid Fat Models

Avoid models handling:

* payments
* external APIs
* emails
* unrelated workflows

Move complex behavior elsewhere.

---

# Simple Database Flow

For small applications:

Route

↓

Model

is acceptable.

Do not force extra layers.

---

# Complex Database Flow

When logic grows:

Route

↓

Service

↓

Model

Use separation when it improves clarity.

---

# Repository Layer

Repositories are optional.

Create only when:

* queries become complex
* data access needs isolation
* multiple storage systems exist

Do not wrap every ORM call automatically.

---

# Avoid Empty Repository Pattern

Bad:

UserRepository.get()

↓

User.query.get()

without added value.

This creates unnecessary navigation.

---

# Query Organization

Keep queries:

* readable
* reusable when needed
* optimized when required

Avoid duplicating complex queries.

---

# Transactions

Use transactions for operations requiring consistency.

Example:

Create order

*

Update inventory

Both succeed.

Or both fail.

---

# Commit Responsibility

Keep commits predictable.

Avoid random commits throughout the application.

Understand where data becomes permanent.

---

# Relationships

Use relationships carefully.

Understand:

* lazy loading
* eager loading
* query impact

Avoid accidental performance problems.

---

# Migrations

Use migration tools.

Example:

Flask-Migrate

Database changes need history.

Never manually modify production schemas.

---

# Constraints

Protect important rules.

Use:

* unique constraints
* foreign keys
* nullable rules

Database should protect data integrity.

---

# Indexing

Add indexes because of:

* query patterns
* performance evidence

Do not index everything.

---

# Raw SQL

Raw SQL is acceptable when:

* ORM becomes inefficient
* database-specific features are required

Use intentionally.

---

# Security

Avoid:

* SQL injection
* unsafe queries
* exposed credentials

Never trust user input.

---

# Performance

Before optimization:

Measure.

Identify problem.

Improve targeted queries.

---

# Testing Database Code

Test:

* important queries
* transactions
* constraints
* failure behavior

Do not test SQLAlchemy itself.

---

# Warning Signs

Review database code when:

* routes contain complex queries
* models handle every workflow
* commits happen everywhere
* repositories only forward calls

---

# SQLAlchemy Checklist

Before completion:

[ ] Models represent data

[ ] Business logic is separated when needed

[ ] Transactions are safe

[ ] Migrations exist

[ ] Queries are understandable

---

# Final Principle

The database layer protects information.

Keep persistence simple, reliable and separate from unnecessary complexity.