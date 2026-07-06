# Data Protection

Data represents user trust.

Protecting data is a core engineering responsibility.

---

# Data Protection Philosophy

Data should be:

* collected carefully
* accessed intentionally
* stored safely
* removed responsibly

Every piece of stored data creates responsibility.

---

# Existing System Rule

Existing data protection strategy has priority.

Before changing:

Understand:

* data model
* compliance requirements
* storage decisions
* access rules

Do not redesign data handling unnecessarily.

---

# Know Your Data

Understand what data exists.

Identify:

* public data
* internal data
* sensitive data
* confidential data

Different data needs different protection.

---

# Collect Required Data Only

Avoid storing data without purpose.

Ask:

Why do we need this?

Unused data still creates risk.

---

# Sensitive Data

Protect:

* personal information
* financial information
* credentials
* private business data

Handle carefully.

---

# Data Access

Access should follow:

least privilege

Users and systems should access only required information.

---

# Data Exposure

APIs should return only necessary fields.

Avoid:

returning entire database objects

Expose intentionally.

---

# Encryption

Use encryption when appropriate.

Protect:

* data in transit
* sensitive data at rest

Based on system requirements.

---

# Encryption Implementation

Use proven libraries and services.

Never create custom encryption algorithms.

---

# Password Data

Passwords require special handling.

Store using:

secure password hashing

Never encrypt and decrypt passwords.

---

# Logging Protection

Never log:

* passwords
* secrets
* sensitive user information

Logs are another storage system.

---

# Backups

Backups contain real data.

Protect:

* backup access
* storage location
* retention

---

# Data Retention

Do not keep data forever without reason.

Define:

* retention needs
* cleanup strategy
* legal requirements

---

# Data Deletion

Deletion should be intentional.

Consider:

* user expectations
* recovery requirements
* compliance

---

# Data Transfers

Protect data moving between systems.

Use secure communication.

Validate destinations.

---

# Third Party Sharing

Before sharing data:

Understand:

* what is shared
* why it is shared
* security impact

---

# Test Data

Avoid using production data in testing.

If required:

remove sensitive information.

---

# Development Environment

Development should not require production data access.

Limit exposure.

---

# Database Permissions

Restrict database access.

Applications should not use unnecessary privileges.

---

# Data Integrity

Protect correctness using:

* validation
* constraints
* transactions

Incorrect data is also failure.

---

# Audit Trails

Important systems may require tracking:

* who changed data
* when changes happened

Based on requirements.

---

# AI Generated Code Rule

Generated code should avoid:

* exposing full objects
* logging sensitive values
* unsafe defaults

Security comes by default.

---

# Warning Signs

Review data handling when:

* everything is returned from APIs
* production data is used casually
* logs contain private information
* nobody knows why data exists

---

# Data Protection Checklist

Before completion:

[ ] Data purpose understood

[ ] Access controlled

[ ] Sensitive fields protected

[ ] Logs reviewed

[ ] Retention considered

---

# Final Principle

Every stored value creates responsibility.

Store carefully.

Protect consistently.