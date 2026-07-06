# Secrets Management

Secrets provide access to systems and data.

They must be protected throughout the application lifecycle.

---

# Secrets Philosophy

A secret should be:

* protected
* limited
* replaceable
* controlled

Treat secrets like production access.

---

# Existing System Rule

Existing secret management has priority.

Before changing:

Understand:

* storage approach
* deployment process
* rotation strategy
* access controls

Do not replace secret systems unnecessarily.

---

# What Is A Secret

Secrets include:

* passwords
* API keys
* tokens
* private keys
* certificates
* database credentials

Protect all of them.

---

# Never Hardcode Secrets

Never place secrets inside:

* source code
* configuration files committed to Git
* documentation
* examples

---

# Environment Variables

Environment variables are acceptable for many deployments.

Examples:

DATABASE_URL

SECRET_KEY

API_TOKEN

Keep configuration outside code.

---

# Secret Managers

Use dedicated secret storage when needed.

Examples:

* cloud secret managers
* deployment platform secrets
* secure vault systems

Choose based on requirements.

---

# Repository Safety

Before committing:

Check for:

* credentials
* private keys
* real environment files

Git history preserves mistakes.

---

# Example Files

Provide examples safely.

Good:

.env.example

Containing:

DATABASE_URL=

API_KEY=

Never include real values.

---

# Logging Secrets

Never log:

* passwords
* access tokens
* refresh tokens
* private keys

Logs can be stored for years.

---

# Error Messages

Errors must not expose:

* credentials
* connection strings
* internal secrets

Fail safely.

---

# Secret Access

Use least privilege.

Applications should access only required secrets.

Avoid sharing one powerful credential everywhere.

---

# Development Secrets

Development credentials should be separate.

Never reuse production secrets locally.

---

# Production Secrets

Production secrets require:

* restricted access
* secure storage
* auditing when needed

---

# Rotation

Secrets should be replaceable.

Plan for:

* leaks
* expiration
* team changes

---

# API Keys

API keys should support:

* limited permissions
* revocation
* regeneration

Avoid permanent unlimited keys.

---

# Database Credentials

Database accounts should have only needed permissions.

Avoid using admin users for applications.

---

# Third Party Services

Protect:

* cloud credentials
* payment keys
* integration tokens

External access is still system access.

---

# CI/CD Secrets

Pipeline secrets require protection.

Avoid:

* printing secrets
* exposing build variables
* unnecessary access

---

# Containers

Never bake secrets into:

* Docker images
* build artifacts

Inject at runtime.

---

# Secret Exposure Response

If a secret leaks:

1. Revoke it

2. Replace it

3. Investigate usage

Do not only remove it from code.

---

# AI Generated Code Rule

Generated examples must never include realistic secrets.

Use placeholders only.

---

# Warning Signs

Review secret handling when:

* credentials exist in Git
* everyone shares one account
* secrets appear in logs
* production and development share keys

---

# Secrets Checklist

Before completion:

[ ] No secrets in code

[ ] Configuration externalized

[ ] Access minimized

[ ] Logs protected

[ ] Rotation possible

---

# Final Principle

A leaked secret is lost access control.

Protect secrets before they become incidents.