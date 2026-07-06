# Django Example

Reference example for Django and Django REST Framework projects.

Follow Django.

Do not rebuild Django.

---

# Goal

Create Django applications that are:

* maintainable
* understandable
* secure
* framework aligned

---

# Recommended Structure

Example:

project/

├── config/

│   ├── settings/

│   ├── urls.py

│   └── wsgi.py

│

└── apps/

```
├── users/

│   ├── models.py

│   ├── serializers.py

│   ├── views.py

│   ├── permissions.py

│   ├── services.py

│   ├── managers.py

│   ├── urls.py

│   └── tests.py
```

---

# App Design Example

Create apps around business areas.

Good:

users

orders

payments

Bad:

utils

logic

database

---

# Model Example

Models contain:

* fields
* relationships
* model-specific behavior

Example:

User

Order

Payment

Models represent domain data.

---

# Serializer Example

Serializers handle:

Input:

validation

Output:

representation

Do not expose unnecessary fields.

---

# View Example

Views handle:

* HTTP request
* permissions
* serializer usage
* responses

Keep views understandable.

---

# Simple View Flow

Request

↓

View

↓

Serializer

↓

Model

↓

Response

Acceptable for simple features.

---

# Service Example

Use services when workflow grows.

Good:

CheckoutService

Handles:

1. Create order

2. Charge payment

3. Update inventory

4. Send email

---

# Bad Service Example

Avoid:

UserView

↓

UserService

↓

User.objects.create()

No value added.

---

# Manager Example

Use managers for reusable queries.

Example:

ActiveUserManager

Purpose:

return active users consistently

---

# Permission Example

Create permission classes for:

* ownership checks
* role checks
* access rules

---

# Authentication Example

Use Django authentication systems.

Avoid custom login systems without reason.

---

# Signal Example

Good signal:

Send notification after independent event.

Bad signal:

Hide important checkout workflow.

Business flow should be visible.

---

# Query Example

Avoid:

query inside loops

Prefer:

optimized ORM usage

Understand database behavior.

---

# Settings Example

Separate:

development

production

Secrets come from environment.

---

# Migration Example

Before migration:

Check:

existing data

production impact

---

# Testing Example

Test:

* permissions
* serializers
* important business rules
* API behavior

---

# Security Example

Always verify:

* authentication
* authorization
* validation
* sensitive fields

---

# Avoid Architecture Example

Do not force:

Controller

Service

Repository

DAO

into every Django project.

Django already provides patterns.

---

# Growth Example

Start:

Models

Views

Serializers

Add:

Services

Managers

Tasks

when complexity requires.

---

# Final Principle

Good Django code feels like Django.

Use the framework before replacing the framework.