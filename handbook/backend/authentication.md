# Authentication

Authentication verifies identity.

It answers one question:

"Who is making this request?"

Authentication must be secure, predictable and consistent.

---

# Authentication Philosophy

Authentication protects system access.

It should be:

* secure by default
* simple to understand
* consistently applied
* difficult to bypass

Never treat authentication as an afterthought.

---

# Authentication vs Authorization

Authentication:

Who are you?

Authorization:

What are you allowed to do?

Keep these responsibilities separate.

A valid user is not automatically allowed to perform every action.

---

# Existing Project Rule

Existing authentication systems have priority.

When modifying projects:

Understand current:

* authentication flow
* token strategy
* session handling
* user model
* security requirements

Do not replace authentication without strong reason.

---

# Identity Verification

Authentication should verify identity using trusted mechanisms.

Examples:

* secure sessions
* access tokens
* identity providers

Never create custom authentication algorithms unnecessarily.

---

# Password Handling

Never store plain passwords.

Passwords must be:

* securely hashed
* salted when applicable
* protected using proven algorithms

Never create custom password storage methods.

---

# Token Handling

Tokens must be treated as secrets.

Protect:

* access tokens
* refresh tokens
* API keys

Never expose tokens through:

* logs
* URLs
* error messages

---

# Token Lifetime

Tokens should have appropriate expiration.

Consider:

* security risk
* user experience
* system requirements

Long-lived access requires stronger protection.

---

# Session Management

Sessions should:

* expire appropriately
* be invalidated when needed
* protect against misuse

Session security matters.

---

# Multi Factor Authentication

Consider stronger authentication when protecting:

* sensitive data
* administrative access
* financial operations

Security level should match risk.

---

# External Authentication Providers

When using providers:

Examples:

* OAuth providers
* identity platforms
* enterprise authentication

Validate:

* tokens
* issuer
* expiration
* expected audience

Never blindly trust external responses.

---

# API Authentication

Protected APIs must clearly define:

* authentication requirements
* accepted credentials
* failure behavior

Authentication should be explicit.

---

# Machine Authentication

Service-to-service communication also needs identity.

Protect:

* internal APIs
* background services
* automation systems

Internal does not mean trusted.

---

# Authentication Errors

Authentication failures should be safe.

Good:

"Invalid credentials"

Bad:

"Password incorrect for this email"

Avoid leaking account information.

---

# Rate Limiting

Protect authentication endpoints.

Consider protection against:

* brute force attempts
* credential stuffing
* abuse

Authentication endpoints are attack targets.

---

# Account Recovery

Recovery flows must be secure.

Protect:

* password resets
* email verification
* account changes

Recovery should not become a security bypass.

---

# Secrets Management

Authentication secrets must come from secure configuration.

Never:

* hardcode secrets
* commit credentials
* expose keys

Rotate secrets when needed.

---

# Logging Authentication

Log security-relevant events:

* failed attempts
* suspicious behavior
* access changes

Never log:

* passwords
* tokens
* credentials

---

# Testing Authentication

Test:

* valid authentication
* invalid credentials
* expired tokens
* missing credentials
* security boundaries

Authentication failures matter.

---

# Authentication Warning Signs

Review when:

* authentication logic is duplicated
* secrets exist in code
* tokens never expire
* authentication rules are unclear
* errors leak information

---

# Authentication Checklist

Before completion:

[ ] Identity verification is secure

[ ] Secrets are protected

[ ] Tokens are handled safely

[ ] Failures are safe

[ ] Sensitive logs are avoided

[ ] Existing security patterns respected

---

# Final Principle

Authentication is the front door of the system.

A strong system starts by knowing who is entering.