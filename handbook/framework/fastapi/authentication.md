# FastAPI Authentication

Authentication verifies the identity of the requester.

FastAPI authentication should be explicit, secure and reusable.

---

# Authentication Philosophy

Authentication should answer:

"Who is making this request?"

It should not decide every action the user can perform.

Authentication and authorization must remain separate.

---

# Existing Project Rule

Existing authentication implementations have priority.

Before changing:

Understand:

* token strategy
* authentication flow
* user model
* security requirements

Do not replace working authentication systems unnecessarily.

---

# Authentication Location

Recommended organization:

core/

├── security.py

api/

├── deps.py

Responsibilities:

core/security.py

* token creation
* token validation
* password utilities

api/deps.py

* current user dependencies
* request authentication

---

# Request Flow

Preferred:

Request

↓

Authentication Dependency

↓

Endpoint

↓

Service

Authentication happens before business execution.

---

# Current User Pattern

Use dependency injection.

Example:

current_user = Depends(
get_current_user
)

Endpoints should clearly show authentication requirements.

---

# Token Handling

Tokens must be treated as secrets.

Never expose:

* access tokens in logs
* refresh tokens
* signing keys

Protect credentials.

---

# JWT Usage

When using JWT:

Validate:

* signature
* expiration
* issuer when needed
* token structure

Never trust decoded data without verification.

---

# Password Security

Never store raw passwords.

Use:

* secure hashing
* proven libraries
* proper verification

Never create custom password algorithms.

---

# Login Flow

Authentication workflow:

Receive credentials

↓

Validate user

↓

Verify password

↓

Generate token/session

↓

Return credentials safely

---

# Keep Business Logic Separate

Avoid:

authentication dependency

↓

creating users

↓

processing business workflows

Authentication identifies users.

Services perform actions.

---

# User Loading

Loading current user is acceptable inside dependencies.

Example:

get_current_user()

This is request preparation.

Not business logic.

---

# Optional Authentication

Some endpoints may support optional identity.

Make this explicit.

Avoid hidden authentication behavior.

---

# Authorization Separation

Authentication:

User exists and identity verified.

Authorization:

User can perform action.

Do not mix all permission logic into authentication.

---

# Refresh Tokens

When using refresh tokens:

Consider:

* expiration
* storage security
* rotation
* revocation

Long-lived access requires protection.

---

# API Keys

For machine access:

Protect:

* API keys
* service credentials

Store securely.

Never hardcode.

---

# Security Configuration

Secrets belong in configuration.

Example:

SECRET_KEY

TOKEN_EXPIRATION

Never commit secrets.

---

# Authentication Errors

Return safe messages.

Good:

Invalid credentials

Avoid:

Email exists but password incorrect

Do not leak account information.

---

# Testing Authentication

Test:

* valid login
* invalid credentials
* expired tokens
* missing authentication
* protected routes

Security flows require tests.

---

# Authentication Warning Signs

Review when:

* JWT decoding appears everywhere
* password logic is duplicated
* tokens are logged
* authentication and business logic mix

---

# Authentication Checklist

Before completing:

[ ] Authentication dependency exists

[ ] Secrets are protected

[ ] Passwords are secure

[ ] Tokens validated properly

[ ] Authorization remains separate

[ ] Existing patterns respected

---

# Final Principle

Authentication proves identity.

Keep it secure, centralized and separate from application behavior.