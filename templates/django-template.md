# Django Template

Django projects should follow Django conventions.

Use the framework.

Do not fight it.

---

# Purpose

Provide Django structure guidance for:

* maintainable apps
* clean APIs
* business logic organization
* secure development

---

# Core Principle

Django already provides structure.

Avoid rebuilding another framework inside Django.

---

# Recommended Structure

Example:

project/

├── config/

│   ├── settings/

│   ├── urls.py

│   └── wsgi.py

│

├── apps/

│   ├── users/

│   ├── orders/

│   └── payments/

│

├── static/

├── media/

├── templates/

└── manage.py

---

# Application Structure

Example:

users/

├── models.py

├── views.py

├── serializers.py

├── urls.py

├── permissions.py

├── services.py

├── managers.py

├── tests.py

└── admin.py

Adjust based on size.

---

# Apps

Create apps around business concepts.

Good:

users

orders

billing

Avoid:

helpers

misc

common

---

# Models

Models represent data.

Responsibilities:

* fields
* relationships
* database rules

Keep them understandable.

---

# Model Methods

Use model methods for behavior directly related to that model.

Avoid putting unrelated workflows inside models.

---

# Managers

Use managers for:

* reusable queries
* model-specific data access

Avoid unnecessary managers.

---

# Serializers

DRF serializers handle:

* validation
* input transformation
* output representation

Keep API contracts clear.

---

# Views And ViewSets

Views handle:

* request flow
* permissions
* responses

Avoid huge views containing all business logic.

---

# Service Layer

Services are optional.

Use services for:

* complex workflows
* multiple model operations
* external integrations

---

# Avoid Empty Services

Do not create:

View

↓

Service

↓

Model.objects.create()

without additional value.

---

# Permissions

Use permission classes for access control.

Always verify:

* authentication
* authorization
* ownership

---

# Authentication

Use proven Django authentication patterns.

Avoid custom authentication unless required.

---

# URLs

Keep routing:

* organized
* predictable
* resource focused

---

# Settings

Separate configuration.

Examples:

development

production

Never hardcode secrets.

---

# Signals

Use signals carefully.

Good:

Decoupled events.

Avoid:

Hidden business workflows.

Code should remain traceable.

---

# Middleware

Use middleware for:

cross-cutting concerns

Examples:

* request handling
* logging
* security

Do not place business logic here.

---

# Forms

Use forms when handling:

* validation
* traditional Django workflows

---

# Admin

Django admin is powerful.

Customize when it improves operations.

---

# Database

Use migrations carefully.

Protect production data.

Follow:

handbook/database/

---

# Testing

Prioritize:

* business rules
* APIs
* permissions
* important workflows

---

# Security

Follow:

handbook/security/

Use Django protections correctly.

---

# Dependency Rules

Check Django built-in features first.

Do not install packages unnecessarily.

---

# AI Generation Rule

Claude should:

* follow existing app patterns
* respect Django conventions
* avoid unnecessary abstractions

---

# Avoid

Never automatically:

* replace Django ORM
* create repository layers everywhere
* move everything into services
* ignore built-in features

---

# Final Principle

The best Django architecture feels like Django.

Simple.

Clear.

Maintainable.