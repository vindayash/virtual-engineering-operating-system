# Environment Template

Environment files configure applications.

Configuration should be separate from code.

Secrets must stay protected.

---

# Purpose

Provide safe environment examples without exposing real credentials.

Use this template for:

.env.example

Never commit real secrets.

---

# Application

APP_NAME=

APP_ENV=development

APP_DEBUG=false

---

# Server Configuration

HOST=0.0.0.0

PORT=8000

---

# Security

SECRET_KEY=

JWT_SECRET=

ENCRYPTION_KEY=

Use placeholders only.

Never add real values.

---

# Database

DATABASE_URL=

DATABASE_HOST=

DATABASE_PORT=

DATABASE_NAME=

DATABASE_USER=

DATABASE_PASSWORD=

---

# Cache

CACHE_HOST=

CACHE_PORT=

CACHE_PASSWORD=

---

# External APIs

SERVICE_API_URL=

SERVICE_API_KEY=

Example:

PAYMENT_API_KEY=

EMAIL_API_KEY=

Never include real keys.

---

# Authentication Providers

OAUTH_CLIENT_ID=

OAUTH_CLIENT_SECRET=

---

# Cloud Configuration

CLOUD_REGION=

CLOUD_ACCESS_KEY=

CLOUD_SECRET_KEY=

Use secure secret management in production.

---

# Storage

STORAGE_BUCKET=

STORAGE_REGION=

STORAGE_ACCESS_KEY=

STORAGE_SECRET_KEY=

---

# Email

EMAIL_HOST=

EMAIL_PORT=

EMAIL_USER=

EMAIL_PASSWORD=

---

# Logging

LOG_LEVEL=INFO

---

# Monitoring

MONITORING_DSN=

ERROR_TRACKING_DSN=

---

# Feature Flags

FEATURE_NAME_ENABLED=false

---

# Environment Rules

Development:

local configuration

Staging:

production-like testing

Production:

secure secret storage

---

# Naming Rules

Use clear names.

Good:

DATABASE_URL

Bad:

DB

---

# Secret Rules

Never include:

* passwords
* tokens
* private keys
* production credentials

---

# Documentation

Explain unusual variables.

Avoid documenting obvious values.

---

# AI Generation Rule

Claude must only generate:

PLACEHOLDER VALUES

Never invent realistic secrets.

---

# Final Checklist

Before committing:

[ ] No real secrets

[ ] Required variables included

[ ] Names are understandable

[ ] Production values removed

---

# Final Principle

Configuration belongs outside code.

Secrets belong outside repositories.