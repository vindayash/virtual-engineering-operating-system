# Project Structure

Project structure exists to make software easier to understand, modify and maintain.

Folders do not create good architecture.

Clear responsibilities create good architecture.

---

# Project Structure Philosophy

A good structure should make it obvious:

* where code belongs
* where changes should happen
* how components interact
* who owns responsibility

Structure should reduce thinking.

Not increase navigation.

---

# Existing Project Rule

Existing project structure has priority.

When working inside existing code:

Do:

* understand current organization
* follow existing patterns
* place code where maintainers expect it
* keep changes consistent

Do not:

* reorganize folders unnecessarily
* introduce personal preferences
* migrate architecture during feature work

Consistency beats ideal structure.

---

# New Project Rule

For new projects:

Start with a simple foundation.

Create separation for:

* configuration
* API interfaces
* business logic
* data models
* external integrations
* tests

Do not create folders without responsibility.

---

# Folder Creation Rule

Before creating a folder ask:

"What responsibility lives here?"

Valid reasons:

* separates concerns
* groups related behavior
* improves navigation
* manages growth

Invalid reasons:

* tutorials use it
* enterprise projects use it
* future code might need it

---

# Avoid Empty Architecture

Do not create structures like:

repositories/

interfaces/

factories/

managers/

providers/

unless they solve current problems.

Empty folders are not architecture.

---

# Growth Based Structure

Allow projects to evolve.

Small:

feature.py

Growing:

feature/
├── api.py
├── logic.py
└── models.py

Large:

feature/
├── routes/
├── services/
├── models/
└── integrations/

Growth creates structure.

Structure should not predict growth.

---

# Feature Organization

Prefer keeping related code close.

A feature should be understandable without searching the entire project.

Avoid spreading simple behavior across many unrelated folders.

---

# Separation Rules

Separate code because responsibilities differ.

Good separation:

API handling

Business rules

Database access

External communication

Bad separation:

Creating layers that only forward calls.

---

# Configuration Structure

Configuration should be:

* centralized
* environment aware
* secure

Avoid:

* scattered settings
* hardcoded values
* duplicated configuration

---

# Utility Code

Avoid creating generic utility folders too early.

Bad:

utils/
├── helpers.py

Large helper files become dumping grounds.

Prefer:

specific modules with clear purpose.

---

# Shared Code

Shared code should exist because reuse exists.

Do not create shared modules for imaginary future reuse.

Duplication is sometimes better than wrong abstraction.

---

# File Size Rule

Large files are not automatically bad.

Split files when:

* responsibilities become mixed
* navigation becomes difficult
* testing becomes harder

Do not split only because line count increased.

---

# Naming Rules

Names should explain purpose.

Prefer:

user_service.py

payment_processor.py

email_sender.py

Avoid:

helper.py

common.py

manager.py

when responsibility is unclear.

---

# Framework Respect Rule

Framework conventions matter.

Do not fight frameworks unnecessarily.

A framework-standard structure is often better than a custom architecture.

---

# Generated Code Rule

When generating new code:

Claude must:

1. Check existing structure

2. Match project style

3. Add minimal required files

4. Avoid unnecessary layers

Never create architecture automatically.

---

# Project Structure Review Checklist

Before adding structure:

Ask:

1. Does this make navigation easier?
2. Does responsibility become clearer?
3. Is this solving today's problem?
4. Will another engineer understand it?
5. Can simpler organization work?

---

# Final Principle

A clean project is not the one with the most folders.

A clean project is the one where every file has an obvious reason to exist.