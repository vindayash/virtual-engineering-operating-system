# Django Views

Views are the entry point between clients and application behavior.

Views handle requests.

They should not become the whole application.

---

# View Philosophy

Views should answer:

"How does the user interact with the system?"

They should not contain every detail of:

"How does the business work?"

Keep responsibilities clear.

---

# Existing Project Rule

Existing view patterns have priority.

Before changing:

Understand:

* current view style
* DRF usage
* service patterns
* response format

Do not rewrite views unnecessarily.

---

# View Responsibility

Views handle:

* HTTP requests
* authentication
* permissions
* serializer usage
* responses

Views coordinate.

They should stay understandable.

---

# DRF Structure

Common patterns:

views.py

or:

views/

├── user.py

├── order.py

Choose based on project size.

Do not split without reason.

---

# APIView vs ViewSet

Choose based on requirement.

Use ViewSets when:

* resource CRUD fits naturally
* router behavior helps

Use APIView when:

* workflow is custom
* endpoint behavior differs

Do not force one pattern everywhere.

---

# Simple Flow

For simple operations:

View

↓

Model / ORM

is acceptable.

Do not create unnecessary services.

---

# Service Flow

For business workflows:

View

↓

Service

↓

Models

Use when complexity exists.

---

# When To Use Services

Create services for:

* multi-step workflows
* transactions
* external integrations
* complex business rules

Example:

Order checkout:

1. Validate inventory

2. Create order

3. Process payment

4. Send email

---

# Avoid Empty Services

Bad:

View

↓

UserService.get_user()

↓

User.objects.get()

This only adds navigation.

---

# Keep Views Thin

Avoid:

* long business workflows
* payment logic
* email generation
* complex calculations

inside views.

---

# Serializers In Views

Views should use serializers for:

* input validation
* output formatting

Do not manually parse everything.

Use framework capabilities.

---

# Query Handling

Simple queries are acceptable.

Example:

queryset = User.objects.all()

Complex queries should move into:

* managers
* querysets
* selectors

when useful.

---

# Permissions

Views should declare permissions clearly.

Example:

permission_classes = [
IsAuthenticated
]

Access rules should be visible.

---

# Authentication

Authentication should use Django/DRF mechanisms.

Avoid custom authentication logic inside views.

---

# Transactions

For complex state changes:

Handle transactions carefully.

Often belongs inside service workflows.

---

# External APIs

Avoid calling third-party systems directly from views.

Prefer services/integration modules.

Views should not know every external detail.

---

# Response Format

Keep API responses consistent.

Follow project conventions.

Do not randomly change formats.

---

# Error Handling

Avoid:

try:

```
everything()
```

except:

```
pass
```

Failures should be explicit.

Use proper exceptions.

---

# Pagination

Use DRF pagination for lists.

Avoid returning unlimited datasets.

Large responses create problems.

---

# Filtering

Use clear filtering patterns.

Avoid unsafe direct user-controlled queries.

Validate input.

---

# View Size

Large views are warning signs.

Split when:

* responsibilities mix
* workflows grow
* testing becomes difficult

Not because of line count only.

---

# Testing Views

Test:

* endpoints
* permissions
* responses
* request validation

Business rules should have separate tests when moved.

---

# Warning Signs

Review views when:

* views contain hundreds of lines
* external integrations live there
* serializers are bypassed
* every change modifies views

---

# View Checklist

Before completion:

[ ] Request handling only

[ ] Serializer used correctly

[ ] Permissions applied

[ ] Business logic separated if needed

[ ] Existing patterns respected

---

# Final Principle

Views connect users to the system.

They should guide requests.

They should not contain the entire journey.