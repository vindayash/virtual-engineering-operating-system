# Python Package Structure

Package structure organizes code so developers can understand and safely modify systems.

A folder structure should represent responsibility.

Not decoration.

---

# Package Philosophy

Good Python structure should make it clear:

* where code belongs
* how modules relate
* what responsibilities exist

The goal is navigation.

Not creating more files.

---

# Existing Project Rule

Existing package structure has priority.

Before changing:

Understand:

* current modules
* import patterns
* framework conventions
* historical reasons

Do not reorganize packages during unrelated work.

---

# New Project Rule

For new projects:

Start with a simple structure.

Add organization when:

* responsibilities grow
* files become unclear
* boundaries appear naturally

Avoid predicting every future requirement.

---

# Avoid Empty Architecture

Do not create folders only because architecture diagrams show them.

Avoid unnecessary:

interfaces/

abstract/

managers/

helpers/

common/

unless they contain clear responsibility.

---

# Module Responsibility

Each module should have a clear reason to exist.

Good:

email_sender.py

payment_processor.py

report_generator.py

Bad:

utils.py

helpers.py

misc.py

Generic modules become dumping grounds.

---

# Imports

Imports should be:

* clear
* predictable
* easy to follow

Avoid:

* circular imports
* hidden dependencies
* wildcard imports

Dependencies should be visible.

---

# Package Boundaries

Separate code when responsibilities differ.

Examples:

API handling

Business workflows

Database interaction

External integrations

Do not separate just to increase layers.

---

# Small Projects

Small applications do not need complex layouts.

Acceptable:

app.py

models.py

services.py

config.py

Simple problems deserve simple structures.

---

# Growing Projects

As projects grow:

Move from:

single files

toward:

responsibility based modules

Growth should drive structure.

---

# Large Projects

Large systems may require:

api/

services/

models/

integrations/

configuration/

Only create these when responsibility exists.

---

# Utility Code

Avoid large utility modules.

Bad:

utils.py containing:

* dates
* emails
* files
* validation

Prefer:

date_utils.py

email_formatter.py

when separation is useful.

---

# **init**.py Usage

Use package initialization carefully.

Avoid hiding too much behavior inside:

**init**.py

Imports should remain understandable.

---

# Configuration Placement

Configuration should be:

* centralized
* environment aware
* easy to locate

Avoid scattering settings everywhere.

---

# Tests Structure

Tests should mirror understanding.

Prefer organization that makes it easy to find:

* what is tested
* why it matters

Follow existing project patterns.

---

# Scripts

Separate scripts when needed.

Examples:

* migrations
* maintenance tasks
* one-time operations

Avoid mixing operational scripts with application logic.

---

# Framework Rules

Respect framework conventions.

Examples:

Django applications should feel like Django.

FastAPI projects should feel like FastAPI.

Do not fight frameworks unnecessarily.

---

# Refactoring Structure

Only restructure when:

* navigation is difficult
* responsibilities are unclear
* duplication causes problems

Never restructure because:

"I prefer this layout."

---

# Package Review Checklist

Before creating packages:

[ ] Does responsibility exist?

[ ] Does this improve understanding?

[ ] Is current structure insufficient?

[ ] Will future developers find code faster?

[ ] Is complexity reduced?

---

# Warning Signs

Review structure when:

* nobody knows where code belongs
* imports become circular
* everything goes into utils
* simple changes touch unrelated modules

---

# Final Principle

A good Python structure feels natural.

Every folder exists because the code needed a home.