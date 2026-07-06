# Django Models

Models represent application data and database structure.

Models protect data integrity.

They should not become the entire application.

---

# Model Philosophy

Django models should define:

* data structure
* relationships
* constraints
* simple data behavior

Keep models meaningful.

Avoid turning models into unrelated business containers.

---

# Existing Project Rule

Existing model patterns have priority.

Before changing:

Understand:

* model organization
* manager usage
* query patterns
* migration history

Do not redesign models unnecessarily.

---

# Model Responsibility

Models should contain:

* fields
* relationships
* constraints
* simple model behavior

Example:

User.full_name()

is reasonable.

---

# Avoid Fat Models

Avoid putting everything into models:

Bad:

User model handling:

* payments
* emails
* reports
* external APIs

Models become difficult to maintain.

---

# Business Workflows

Complex workflows belong outside models.

Example:

Order checkout:

* validate inventory
* calculate price
* process payment
* send email

Use a service.

---

# Model Methods

Use model methods for behavior belonging to that object.

Good:

order.is_cancelable()

The order owns this rule.

---

# Avoid Model Helpers

Avoid:

User.do_everything()

Large generic methods hide responsibilities.

---

# Field Design

Fields should be:

* intentional
* correctly typed
* constrained

Avoid storing unclear data.

---

# Database Constraints

Protect important rules.

Use:

* unique constraints
* foreign keys
* indexes
* validation constraints

Do not rely only on application checks.

---

# Relationships

Design relationships carefully.

Understand:

* ForeignKey
* OneToOne
* ManyToMany

Relationships affect performance and ownership.

---

# Related Names

Use meaningful related names.

Good:

user.orders

Avoid confusing defaults when relationships grow.

---

# Query Performance

Be aware of:

select_related

prefetch_related

Avoid unnecessary database queries.

---

# Managers

Managers handle reusable query behavior.

Good:

User.objects.active()

Avoid:

managers becoming business service layers.

---

# QuerySets

Custom QuerySets are useful for:

* reusable filters
* chainable queries

Keep query responsibility clear.

---

# Selectors

Optional selectors may handle:

* complex reads
* optimized queries
* reporting queries

Do not create selectors for simple ORM calls.

---

# Model Validation

Use model validation for data integrity.

Do not put full workflows into validation methods.

---

# Signals And Models

Avoid depending heavily on signals.

Hidden model side effects make behavior difficult to trace.

Prefer explicit workflows.

---

# Migrations

All model changes require migrations.

Migrations should be:

* reviewed
* committed
* tested

Database history matters.

---

# Data Migrations

Data migrations require care.

Consider:

* existing production data
* rollback strategy
* execution time

Production databases are valuable.

---

# Indexes

Create indexes based on:

* query patterns
* performance problems
* measurements

Do not index everything.

---

# Choices And Enums

Use choices/enums for fixed states.

Example:

OrderStatus

Avoid magic strings throughout code.

---

# Timestamps

Important models should track:

* creation time
* update time

when auditing is needed.

---

# Security

Never store:

* plain passwords
* secrets
* sensitive tokens

without proper protection.

---

# Testing Models

Test:

* important model behavior
* constraints
* custom queries
* state rules

Do not test Django itself.

---

# Warning Signs

Review models when:

* one model controls everything
* external APIs are called from models
* models contain unrelated workflows
* queries are duplicated everywhere

---

# Model Checklist

Before completing:

[ ] Data ownership is clear

[ ] Constraints exist where needed

[ ] Queries are efficient

[ ] Business workflows are separated

[ ] Migration impact considered

---

# Final Principle

Models protect data.

Keep them powerful enough to represent data.

Not so powerful they become the whole system.