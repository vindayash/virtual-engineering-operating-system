# Django Project Structure

Django projects should follow Django principles while keeping responsibilities clear.

Use the framework.

Do not fight the framework.

---

# Django Philosophy

Django already provides structure.

A good Django project should:

* respect Django conventions
* keep apps focused
* separate responsibilities when useful
* avoid unnecessary architecture layers

Django is designed to be productive.

---

# Existing Project Rule

Existing Django architecture has priority.

Before changing:

Understand:

* current apps
* project layout
* conventions
* historical decisions

Do not restructure a working Django project unnecessarily.

---

# New Project Standard

For new projects prefer:

project/

├── config/

│   ├── settings/

│   ├── urls.py

│   ├── celery.py

│   └── wsgi.py

├── apps/

│   ├── users/

│   ├── payments/

│   └── orders/

├── requirements/

└── manage.py

Separate project configuration from business apps.

---

# App Structure

Recommended:

users/

├── models.py

├── views.py

├── serializers.py

├── permissions.py

├── services.py

├── selectors.py

├── tasks.py

├── urls.py

└── tests/

Add files only when needed.

---

# Do Not Create Empty Layers

Avoid creating:

services.py

selectors.py

managers.py

for every app automatically.

Files should appear when responsibility exists.

---

# Apps

Apps represent business domains.

Good:

users

orders

billing

Avoid unclear apps:

common

helpers

core

unless they have a defined purpose.

---

# Views Responsibility

Views handle:

* HTTP requests
* authentication
* permissions
* serializer usage
* responses

Views are the API entry point.

---

# Service Layer

Services are optional.

Use services for:

* workflows
* transactions
* multi-model operations
* external integrations

Do not create services that only call models.

---

# Simple Django Flow

Acceptable:

View

↓

Model

for simple operations.

Do not force unnecessary layers.

---

# Complex Django Flow

For workflows:

View

↓

Service

↓

Models

Example:

Create order:

* validate inventory
* create order
* process payment
* send email

belongs in service.

---

# Selectors

Selectors are optional.

Use selectors for:

* complex queries
* reusable reads
* optimized fetching

Avoid:

UserSelector.get_user()

that only wraps:

User.objects.get()

---

# Models

Models handle:

* database fields
* relationships
* constraints
* simple model behavior

Avoid turning models into giant business objects.

---

# Serializers

Serializers handle:

* input validation
* output representation
* transformation

Do not place workflows inside serializers.

---

# Managers

Use custom managers for:

* reusable query behavior
* model-specific querying

Avoid using managers as service replacements.

---

# Signals

Use signals carefully.

Signals hide execution flow.

Prefer explicit calls for important business workflows.

---

# Configuration

Settings should be:

* environment based
* secure
* separated by environment when needed

Never hardcode secrets.

---

# Shared Code

Avoid dumping everything into:

utils.py

Prefer purpose-based modules.

Example:

email_sender.py

file_validator.py

---

# Django REST Framework

DRF conventions should be respected.

Do not recreate functionality DRF already provides.

Use:

* serializers
* permissions
* authentication
* pagination

properly.

---

# Background Tasks

Use Celery/background workers only when needed.

Not every operation needs async execution.

---

# Growth Rule

Start:

View

↓

Model

Grow:

View

↓

Service

↓

Model

when complexity appears.

Architecture follows requirements.

---

# Warning Signs

Review structure when:

* every app has empty files
* simple changes touch many layers
* business logic exists everywhere
* apps have unclear ownership

---

# Structure Checklist

Before creating files:

[ ] Does responsibility exist?

[ ] Is Django convention followed?

[ ] Is service layer needed?

[ ] Is complexity justified?

[ ] Existing structure respected?

---

# Final Principle

Good Django architecture feels like Django.

Improve the framework.

Do not rebuild another framework inside it.