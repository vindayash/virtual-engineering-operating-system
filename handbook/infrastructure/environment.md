# Environment Management

Environment configuration controls how software behaves outside code.

Applications should be portable.

Configuration should change.

Code should not.

---

# Environment Philosophy

Separate:

Application logic

from

Deployment configuration

The same application should run in different environments safely.

---

# Existing Project Rule

Existing environment strategy has priority.

Before changing:

Understand:

* configuration loading
* secret management
* deployment process

Do not replace working environment systems unnecessarily.

---

# Environment Types

Common environments:

Development

Staging

Production

Each has different purpose.

---

# Development

Development should support:

* local debugging
* fast iteration
* safe experimentation

Never connect accidentally to production resources.

---

# Staging

Staging should represent production behavior.

Used for:

* verification
* testing releases
* integration testing

Keep it realistic.

---

# Production

Production requires:

* security
* reliability
* monitoring
* controlled changes

Treat production carefully.

---

# Environment Variables

Use environment variables for:

* deployment configuration
* credentials
* external services

Examples:

DATABASE_URL

REDIS_URL

API_KEYS

---

# Secrets

Secrets include:

* passwords
* private keys
* tokens
* credentials

Never commit secrets.

---

# .env Files

.env files are useful locally.

Do not commit real environment files.

Commit examples only.

Example:

.env.example

---

# .env Example Files

Provide:

DATABASE_URL=

SECRET_KEY=

API_URL=

without real values.

Help setup without exposing secrets.

---

# Configuration Loading

Centralize configuration.

Avoid:

reading environment variables everywhere.

Application should have one configuration source.

---

# Required Variables

Validate required configuration during startup.

Fail early.

Avoid discovering missing values during user requests.

---

# Defaults

Defaults are acceptable for safe values.

Examples:

PAGE_SIZE=20

TIMEOUT=30

Never default production secrets.

---

# Environment Separation

Avoid sharing:

* databases
* credentials
* storage

between unrelated environments.

---

# Feature Flags

Feature flags can control:

* gradual releases
* experiments
* temporary behavior

Remove unused flags.

---

# Logging Configuration

Different environments need different logging.

Development:

debug information.

Production:

safe operational information.

---

# Debug Mode

Never enable debug mode in production.

Debug output can expose sensitive information.

---

# Access Control

Limit access to production configuration.

Only required people and systems should access secrets.

---

# Rotation

Important secrets should support rotation.

Plan for:

* leaked keys
* expired credentials
* security updates

---

# Infrastructure Configuration

Infrastructure should also follow environment separation.

Examples:

* storage buckets
* queues
* databases

---

# Documentation

Document required variables.

Developers should know what configuration exists.

---

# Warning Signs

Review environment setup when:

* production values exist locally
* secrets are committed
* changing environment requires code edits
* configuration is duplicated everywhere

---

# Environment Checklist

Before completion:

[ ] Secrets outside source code

[ ] Configuration centralized

[ ] Environments separated

[ ] Required values documented

[ ] Production protected

---

# Final Principle

Code defines behavior.

Environment defines where and how it runs.

Never mix them.