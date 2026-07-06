# Secure Coding

Secure coding prevents vulnerabilities during development.

Security should be part of engineering.

Not something added after completion.

---

# Secure Coding Philosophy

Good software should be:

* functional
* reliable
* maintainable
* secure

A feature is incomplete if it introduces avoidable security risks.

---

# Existing Project Rule

Existing security architecture has priority.

Before changing:

Understand:

* authentication flow
* authorization rules
* data handling
* security requirements

Do not replace security systems unnecessarily.

---

# Secure By Default

Prefer safe behavior automatically.

Examples:

* deny access by default
* validate input
* protect secrets
* expose minimal data

Users and developers make mistakes.

Systems should reduce risk.

---

# Never Trust Input

All external input is untrusted.

Examples:

* API requests
* files
* headers
* query parameters
* third-party callbacks

Validate before usage.

---

# Input Validation

Validate:

* required fields
* types
* formats
* allowed values
* size limits

Invalid data should fail safely.

---

# Output Safety

Be careful when returning information.

Avoid exposing:

* internal errors
* stack traces
* secrets
* unnecessary data

---

# Error Handling

Errors should help developers.

Not attackers.

Good:

Invalid request

Bad:

Database table users_private failed

---

# Secrets In Code

Never hardcode:

* passwords
* API keys
* tokens
* certificates

Secrets belong in secure configuration.

---

# Authentication

Authentication verifies identity.

Always use proven approaches.

Avoid custom security algorithms.

---

# Authorization

Authorization verifies permission.

A logged-in user should not automatically access everything.

Always check access.

---

# Password Handling

Never:

* store plain passwords
* create custom hashing
* log passwords

Use proven password hashing methods.

---

# Encryption

Use established libraries.

Do not create custom encryption.

Security algorithms require expert review.

---

# Database Security

Prevent:

* injection attacks
* unsafe queries
* unauthorized access

Use:

* parameterized queries
* ORM protections correctly

---

# File Handling

Uploaded files require validation.

Check:

* type
* size
* storage location
* permissions

Never blindly trust files.

---

# External Services

Treat external responses as untrusted.

Validate:

* API responses
* webhook payloads
* integrations

---

# Dependency Security

Third-party packages become part of your application.

Review:

* maintenance
* vulnerabilities
* necessity

---

# Sensitive Data

Identify sensitive information.

Protect:

* personal data
* credentials
* financial data
* private records

---

# Logging

Never log:

* passwords
* tokens
* secrets
* sensitive payloads

Logs can leak information.

---

# Access Control

Use least privilege.

Give:

only required access

Avoid:

everything access

---

# Security And Convenience

Avoid shortcuts like:

"temporary disabled authentication"

Temporary security bypasses often remain forever.

---

# AI Generated Code Rule

Generated code must follow security rules.

Never generate:

* insecure defaults
* exposed secrets
* disabled protections

for convenience.

---

# Security Review

Review changes affecting:

* authentication
* authorization
* payments
* user data
* infrastructure

with extra care.

---

# Warning Signs

Review code when:

* users access data without ownership checks
* secrets appear in files
* validation is missing
* errors expose internals
* security is planned "later"

---

# Secure Coding Checklist

Before completion:

[ ] Inputs validated

[ ] Access verified

[ ] Secrets protected

[ ] Errors are safe

[ ] Dependencies reviewed

[ ] Sensitive data protected

---

# Final Principle

Security is not a separate phase.

Secure code is simply complete code.