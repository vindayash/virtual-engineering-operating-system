# Authentication Security

Authentication verifies identity.

It answers:

"Who is this user or system?"

Authentication must be secure, predictable and carefully designed.

---

# Authentication Philosophy

Authentication protects entry into the system.

Use proven approaches.

Avoid inventing security mechanisms.

Security requires reliability over creativity.

---

# Existing System Rule

Existing authentication systems have priority.

Before changing:

Understand:

* authentication flow
* token strategy
* user model
* sessions
* security requirements

Do not replace working authentication unnecessarily.

---

# Authentication vs Authorization

Authentication:

Who are you?

Authorization:

What can you access?

Keep these responsibilities separate.

---

# Use Proven Solutions

Prefer:

* trusted frameworks
* maintained libraries
* established protocols

Avoid custom authentication implementations.

---

# Password Storage

Never store passwords directly.

Never store:

* plain text passwords
* reversible passwords

Use secure hashing algorithms.

---

# Password Hashing

Use proven algorithms.

Examples:

* bcrypt
* Argon2

Avoid:

* MD5
* SHA1
* custom hashing

---

# Login Security

Login systems should protect against:

* credential guessing
* information leakage
* abuse

Handle failures safely.

---

# Authentication Errors

Avoid revealing account details.

Good:

Invalid credentials

Bad:

Email exists but password incorrect

---

# Session Authentication

For session systems:

Protect:

* session identifiers
* cookies
* expiration rules

Sessions represent identity.

---

# Cookie Security

Use appropriate cookie protections.

Consider:

* HttpOnly
* Secure
* SameSite

based on application needs.

---

# Token Authentication

Tokens should be:

* signed
* validated
* time limited

Never trust token content without verification.

---

# JWT Security

When using JWT:

Validate:

* signature
* expiration
* issuer when required
* claims when required

Decoded does not mean trusted.

---

# Access Tokens

Access tokens should usually be short lived.

Reduce damage if exposed.

---

# Refresh Tokens

Protect refresh tokens carefully.

Consider:

* rotation
* expiration
* revocation

They provide long-term access.

---

# Token Storage

Store tokens based on application type and threat model.

Understand risks:

* XSS
* CSRF
* device compromise

---

# API Keys

API keys identify systems.

Protect them like passwords.

Support:

* rotation
* revocation
* limited permissions

---

# OAuth

Use OAuth when integrating external identity providers.

Follow provider recommendations.

Do not modify protocol behavior.

---

# Multi Factor Authentication

Consider MFA for:

* administrative access
* sensitive systems
* high-risk operations

---

# Account Recovery

Recovery flows are security features.

Protect:

* password reset tokens
* email verification
* identity changes

---

# Rate Limiting

Protect authentication endpoints.

Examples:

* login attempts
* password resets
* OTP verification

Prevent abuse.

---

# Logging Authentication

Log important events:

* successful login
* failures
* suspicious activity

Never log credentials.

---

# Authentication State

Be able to invalidate access.

Examples:

* user disabled
* password changed
* security incident

---

# Machine Authentication

Services also require identity.

Protect:

* service tokens
* certificates
* API credentials

---

# Testing Authentication

Test:

* valid login
* invalid login
* expired credentials
* revoked access
* edge cases

---

# Warning Signs

Review authentication when:

* custom crypto exists
* passwords are handled manually
* tokens never expire
* authentication logic is duplicated everywhere

---

# Authentication Checklist

Before completion:

[ ] Passwords stored safely

[ ] Tokens validated

[ ] Expiration handled

[ ] Credentials protected

[ ] Failures handled safely

[ ] Existing system respected

---

# Final Principle

Authentication proves identity.

Build it with trusted patterns, not assumptions.