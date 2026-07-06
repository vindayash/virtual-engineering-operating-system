# Flask Project Structure

Flask applications should be simple, organized and intentional.

Flask provides flexibility.

Do not turn flexibility into chaos.

---

# Flask Philosophy

A good Flask structure should:

* keep responsibilities clear
* remain easy to understand
* grow naturally

Start simple.

Add structure when needed.

---

# Existing Project Rule

Existing Flask structure has priority.

Before changing:

Understand:

* current application layout
* extension setup
* routing style
* conventions

Do not restructure working Flask projects unnecessarily.

---

# Small Application Structure

Small applications can remain simple.

Example:

app.py

models.py

config.py

This is acceptable.

Do not create unnecessary architecture.

---

# Growing Application Structure

When complexity grows:

app/

├── **init**.py

├── routes/

├── models/

├── schemas/

├── services/

├── extensions.py

└── config.py

Add folders because responsibilities exist.

---

# Large Application Structure

For larger systems:

app/

├── blueprints/

├── models/

├── services/

├── repositories/

├── extensions/

├── middleware/

├── config/

└── utils/

Only introduce layers with purpose.

---

# Application Factory Pattern

Prefer application factory for scalable projects.

Example:

create_app()

Benefits:

* testing
* configuration
* initialization control

Do not force it for tiny scripts.

---

# Blueprint Organization

Use blueprints for:

* feature separation
* route organization
* modular systems

Example:

users/

orders/

payments/

---

# Avoid Giant app.py

Avoid:

app.py containing:

* routes
* database logic
* business rules
* configuration
* integrations

Growth requires separation.

---

# Avoid Over Engineering

Do not automatically create:

* repositories
* managers
* interfaces
* factories

without actual complexity.

---

# Route Responsibility

Routes handle:

* HTTP requests
* validation
* responses

Avoid large workflows inside routes.

---

# Service Layer

Services are optional.

Use services for:

* business workflows
* multiple operations
* external integrations

Do not create services that only forward calls.

---

# Simple Flow

Acceptable:

Route

↓

Model

for small CRUD applications.

---

# Complex Flow

Use:

Route

↓

Service

↓

Database

when business logic grows.

---

# Models

Models represent:

* database structure
* relationships
* persistence

Avoid placing unrelated workflows inside models.

---

# Extensions

Initialize extensions centrally.

Example:

extensions.py

Containing:

db

cache

login manager

Avoid scattered initialization.

---

# Configuration

Configuration should support environments.

Examples:

* development
* testing
* production

Never hardcode secrets.

---

# Utilities

Avoid:

utils.py

becoming a dumping ground.

Prefer:

email.py

file_handler.py

with clear ownership.

---

# Migrations

Database changes should use migration tools.

Production schemas need history.

---

# Testing Structure

Recommended:

tests/

├── test_routes.py

├── test_services.py

└── conftest.py

Match project complexity.

---

# Growth Rule

Simple:

Routes

↓

Models

Advanced:

Routes

↓

Services

↓

Models

Architecture follows requirements.

---

# Warning Signs

Review structure when:

* app.py becomes huge
* everything imports everything
* business logic appears everywhere
* simple changes require many files

---

# Structure Checklist

Before adding structure:

[ ] Does responsibility exist?

[ ] Does it reduce complexity?

[ ] Is Flask simplicity preserved?

[ ] Existing patterns respected?

---

# Final Principle

Flask gives freedom.

Good engineering decides how much structure the application actually needs.