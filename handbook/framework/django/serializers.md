# Django REST Framework Serializers

Serializers define API input and output contracts.

They transform data between the application and external clients.

---

# Serializer Philosophy

Serializers should handle:

* validation
* serialization
* representation
* API contracts

They should not become business workflow engines.

---

# Existing Project Rule

Existing serializer patterns have priority.

Before changing:

Understand:

* serializer organization
* validation style
* response patterns
* project conventions

Do not rewrite serializers unnecessarily.

---

# Serializer Responsibility

Serializers answer:

"What data is allowed?"

"What does the API return?"

They should not answer:

"What business process should run?"

---

# Location

Standard:

apps/

└── users/

```
├── serializers.py
```

or for larger apps:

serializers/

├── user.py

├── profile.py

Grow structure naturally.

---

# Naming

Use clear names.

Good:

UserCreateSerializer

UserUpdateSerializer

UserResponseSerializer

Avoid:

UserSerializer2

NewUserSerializer

---

# Request And Response Separation

Separate serializers when responsibilities differ.

Example:

Input:

UserCreateSerializer

Output:

UserDetailSerializer

Avoid exposing fields accidentally.

---

# ModelSerializer Usage

Use ModelSerializer when it helps.

Good:

CRUD APIs

model-based resources

Avoid forcing it when:

* data does not represent a model
* custom structures are needed

---

# Field Control

Always explicitly control fields.

Prefer:

fields = [
"id",
"email",
"name"
]

Avoid:

fields = "**all**"

for public APIs.

Prevent accidental exposure.

---

# Sensitive Fields

Never expose:

* passwords
* tokens
* secrets
* internal flags

through serializers.

---

# Validation Responsibility

Good serializer validation:

* required fields
* formats
* allowed values
* input consistency

Example:

email format

date range

---

# Business Logic Validation

Avoid putting workflows in serializers.

Bad:

* processing payments
* sending emails
* creating multiple systems

Move to services.

---

# Create And Update Methods

Serializer create/update is acceptable for simple operations.

Example:

creating one model instance.

For workflows:

Use services.

---

# Nested Serializers

Use nested serializers carefully.

Good:

When response clarity improves.

Avoid:

Huge nested objects causing performance issues.

---

# Serializer Performance

Watch for:

* N+1 queries
* expensive properties
* large relationships

Optimize queries outside serializers.

---

# SerializerMethodField

Use carefully.

Good:

small calculated values.

Avoid:

* database-heavy logic
* external API calls
* business workflows

---

# Read Only Fields

Protect system-controlled values.

Example:

created_at

updated_at

id

should usually be read-only.

---

# Write Only Fields

Use write-only for sensitive inputs.

Example:

password

Input needed.

Output unsafe.

---

# Validation Errors

Return:

* clear errors
* safe messages
* consistent format

Avoid leaking internals.

---

# Reuse

Reuse serializers when responsibility matches.

Do not force one serializer for every situation.

Different APIs may need different contracts.

---

# Testing Serializers

Test:

* validation rules
* required fields
* sensitive field protection
* transformations

Do not test DRF itself.

---

# Warning Signs

Review serializers when:

* serializers contain workflows
* APIs expose all model fields
* database queries happen inside serializers
* one serializer handles everything

---

# Serializer Checklist

Before completion:

[ ] Fields explicitly controlled

[ ] Sensitive data hidden

[ ] Validation belongs here

[ ] Business logic separated

[ ] Response contract is clear

---

# Final Principle

Serializers protect API boundaries.

They decide how data moves.

They should not decide how business works.