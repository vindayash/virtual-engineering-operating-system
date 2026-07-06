# Python Typing

Type hints improve understanding, maintainability and reliability.

Typing should make Python easier to work with.

Not harder.

---

# Typing Philosophy

Types are communication.

They explain:

* expected inputs
* returned values
* data structures
* developer intent

Use typing to reduce confusion.

Do not use typing to show complexity.

---

# Existing Project Rule

Existing typing style has priority.

When modifying projects:

Follow current:

* typing strictness
* conventions
* patterns

Do not introduce large typing migrations during unrelated work.

Improve gradually.

---

# When To Use Types

Prefer type hints for:

* function parameters
* return values
* public interfaces
* service boundaries
* complex data structures

Types are most valuable at boundaries.

---

# Function Typing

Good:

def calculate_total(
price: float,
quantity: int
) -> float:
...

The contract is clear.

---

Avoid unclear functions:

def calculate(data):
...

when meaning is unknown.

---

# Return Types

Always make important return values clear.

Good:

def get_user(user_id: int) -> User | None:
...

The caller understands possible outcomes.

---

# Avoid Overly Complex Types

Avoid creating types nobody can understand.

Bad:

Deep nested generics requiring investigation.

Types should reduce mental effort.

Not increase it.

---

# Type Everything?

Not every variable needs annotation.

Good:

users = get_active_users()

Unnecessary:

users: list[User] = get_active_users()

when already obvious.

---

# Optional Values

Be explicit when values can be missing.

Good:

User | None

Avoid hiding missing states.

Handle None properly.

---

# Any Usage

Avoid unnecessary Any.

Any removes type safety.

Use only when:

* data is truly dynamic
* external libraries require it
* temporary migration needs it

---

# Collections

Prefer specific collection types.

Good:

list[str]

dict[str, int]

Better contracts create fewer mistakes.

---

# Models And Schemas

Use proper models for structured data.

Prefer:

* dataclasses
* framework schemas
* validation models

when data has meaning.

Avoid passing random dictionaries everywhere.

---

# Dictionaries

Dictionary usage is acceptable.

But avoid:

dict

for important business objects.

Prefer meaningful structures.

---

# Type Aliases

Use aliases when they improve understanding.

Example:

UserId = int

Only when the meaning matters.

Do not create aliases unnecessarily.

---

# Protocols And Interfaces

Use advanced typing features only when they solve problems.

Avoid creating:

* protocols
* generics
* abstractions

without actual need.

---

# Runtime Validation

Type hints do not validate runtime data.

External input still requires validation.

Typing helps developers.

Validation protects systems.

---

# Third Party Data

For external responses:

Do not blindly trust types.

Validate:

* API responses
* files
* user input

External data can be wrong.

---

# Gradual Typing

Python supports gradual improvement.

For legacy projects:

Add types:

* around changed code
* critical functions
* confusing areas

Avoid rewriting everything.

---

# Type Checking

Use type checkers when they provide value.

They should:

* catch mistakes
* improve confidence
* support refactoring

They should not slow development unnecessarily.

---

# Documentation

Good typing reduces documentation needs.

Example:

def send_email(
recipient: EmailAddress,
message: str
) -> bool:

is clearer than comments explaining parameters.

---

# Typing Warning Signs

Review typing when:

* types are harder than code
* developers ignore type errors
* everything becomes Any
* simple changes require typing changes everywhere

---

# Typing Checklist

Before completing:

[ ] Important functions have types

[ ] Return values are clear

[ ] None cases are handled

[ ] Types improve readability

[ ] Complexity is justified

---

# Final Principle

Good typing makes Python easier to understand.

If typing makes simple code confusing, reconsider the approach.