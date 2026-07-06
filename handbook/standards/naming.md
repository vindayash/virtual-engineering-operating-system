# Naming Standards

Names communicate intent.

Good names reduce the need for explanations.

---

# Naming Philosophy

A good name should explain:

* what something represents
* why it exists
* how it should be understood

Code should read naturally.

---

# Existing Project Rule

Existing naming conventions have priority.

Before changing:

Understand:

* project style
* framework conventions
* team decisions

Do not rename working code only because of preference.

Consistency matters.

---

# Clarity Over Shortness

Prefer understandable names.

Good:

calculate_invoice_total()

Bad:

calc()

unless the abbreviation is universally understood.

---

# Avoid Overly Generic Names

Avoid:

data

info

manager

handler

processor

unless the responsibility is truly clear.

Generic names hide meaning.

---

# Variables

Variables should describe the value.

Good:

active_users

payment_status

retry_count

Bad:

x

temp

value

except for obvious short scopes.

---

# Functions

Functions should describe actions.

Usually start with verbs.

Examples:

create_user()

calculate_price()

send_email()

A function name should reveal behavior.

---

# Boolean Names

Booleans should read like conditions.

Good:

is_active

has_permission

can_delete

Bad:

active_flag

permission_check

---

# Classes

Classes represent concepts.

Good:

PaymentService

UserRepository

EmailSender

Bad:

Helper

Common

Utility

---

# Services

Service names should describe responsibility.

Good:

PaymentService

ReportGenerator

Avoid:

MainService

GeneralService

---

# Modules And Files

Files should explain contents.

Good:

email_sender.py

password_validator.py

Bad:

helpers.py

misc.py

---

# Constants

Constants should clearly represent fixed values.

Example:

MAX_LOGIN_ATTEMPTS

Avoid unexplained magic values.

---

# Database Tables

Tables represent entities.

Good:

users

orders

payment_transactions

Bad:

details

records

data

---

# Database Columns

Columns should describe stored information.

Good:

created_at

payment_status

email_verified

Avoid unclear abbreviations.

---

# API Routes

Routes should represent resources.

Good:

/users

/orders/{id}

Avoid:

/getUserData

/doAction

---

# API Fields

API names become contracts.

Choose carefully.

Changing them affects users.

---

# Test Names

Tests should describe behavior.

Good:

test_user_cannot_access_private_order

Bad:

test_order

---

# Avoid Encoding Implementation

Avoid names tied to temporary implementation.

Example:

sql_user_service

when storage may change.

---

# Avoid Misleading Names

A wrong name is worse than a long name.

If behavior changes:

Update the name.

---

# Abbreviations

Use abbreviations only when commonly understood.

Good:

id

url

api

Avoid project-specific shortcuts.

---

# Length

Names should be as long as needed.

Not shorter.

Not unnecessarily verbose.

---

# Naming During Refactoring

Rename carefully.

Consider:

* public APIs
* database fields
* external contracts

Some names are expensive to change.

---

# Warning Signs

Review naming when:

* comments explain variable purpose
* every file has helper/common names
* developers constantly search usage
* names no longer match behavior

---

# Naming Checklist

Before completion:

[ ] Name explains purpose

[ ] Existing convention followed

[ ] Generic terms avoided

[ ] Abbreviations are clear

[ ] Future readers can understand

---

# Final Principle

Names are documentation used every day.

Choose names that reduce thinking, not typing.