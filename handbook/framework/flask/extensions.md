# Flask Extensions

Extensions add reusable functionality to Flask applications.

They should be initialized consistently and managed carefully.

---

# Extension Philosophy

Extensions should:

* solve real problems
* integrate cleanly
* remain maintainable

Do not add extensions unnecessarily.

Every extension becomes part of the system.

---

# Existing Project Rule

Existing extension patterns have priority.

Before changing:

Understand:

* initialization style
* extension usage
* application setup

Do not migrate extension architecture unnecessarily.

---

# Extension Location

Recommended:

extensions.py

Example:

db = SQLAlchemy()

jwt = JWTManager()

cache = Cache()

Initialize once.

Configure later.

---

# Application Factory Pattern

Preferred:

extensions.py

db = SQLAlchemy()

app factory:

def create_app():

```
app = Flask(__name__)

db.init_app(app)
```

This avoids tight coupling.

---

# Avoid Direct App Binding

Avoid:

db = SQLAlchemy(app)

in larger applications.

It makes:

* testing harder
* configuration harder
* multiple apps harder

---

# When To Add Extensions

Add extensions when they provide:

* clear functionality
* maintained solutions
* reduced complexity

Examples:

* database ORM
* authentication
* migrations
* caching

---

# Avoid Extension Bloat

Do not install extensions for:

* tiny helpers
* simple functions
* problems Python already solves

Dependencies create ownership.

---

# Extension Responsibility

Extensions provide capabilities.

They should not own business logic.

Example:

JWT extension:

handles tokens.

Application:

handles permissions.

---

# Configuration

Configure extensions through application settings.

Avoid:

hardcoded extension values.

Configuration belongs separately.

---

# Database Extensions

Database extensions should:

* initialize once
* manage connections correctly
* integrate with migrations

Avoid multiple competing database setups.

---

# Authentication Extensions

Authentication extensions help with:

* tokens
* sessions
* identity handling

Authorization rules remain application responsibility.

---

# Cache Extensions

Use caching only when needed.

Before caching:

Measure performance problems.

Do not cache imaginary bottlenecks.

---

# Migration Extensions

Database migrations should be managed consistently.

Schema history matters.

Never manually patch production databases.

---

# Extension Usage

Keep usage predictable.

Avoid importing extensions from random places.

Prefer:

from app.extensions import db

---

# Testing Extensions

Factory initialization allows:

* test configuration
* mock services
* isolated environments

Design for testing.

---

# Updating Extensions

Review:

* breaking changes
* security fixes
* compatibility

Do not blindly upgrade production dependencies.

---

# Removing Extensions

Remove extensions when:

* unused
* replaced
* security risk exists

Unused dependencies still create risk.

---

# Warning Signs

Review extensions when:

* initialization happens everywhere
* circular imports appear
* extensions control business logic
* nobody knows why dependency exists

---

# Extension Checklist

Before adding:

[ ] Problem exists

[ ] Extension is maintained

[ ] Configuration is separated

[ ] Initialization is clean

[ ] Testing remains simple

---

# Final Principle

Extensions should make Flask stronger.

They should not make the application harder to understand.