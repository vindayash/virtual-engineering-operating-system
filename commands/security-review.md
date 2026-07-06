# Command: Security Review

Review application security systematically.

Find real risks.

Prioritize safe improvements.

---

# Purpose

Identify:

* vulnerabilities
* unsafe patterns
* data exposure risks
* security weaknesses

without unnecessary rewrites.

---

# Required Behavior

Understand the system first.

Security recommendations must consider:

* architecture
* requirements
* existing protections
* actual risk

---

# Active Agents

Use:

* Security Agent
* Backend Agent
* Database Agent
* Infrastructure knowledge

when required.

---

# Step 1: Understand Application

Identify:

* application type
* users
* sensitive data
* security boundaries

Different systems have different risks.

---

# Step 2: Authentication Review

Check:

* login flow
* token handling
* sessions
* password handling

Verify identity is protected.

---

# Step 3: Authorization Review

Check:

* permissions
* ownership validation
* role handling
* access restrictions

Never assume authentication is enough.

---

# Step 4: API Security Review

Analyze:

* input validation
* response exposure
* error handling
* rate limiting

APIs are entry points.

---

# Step 5: Data Protection Review

Check:

* sensitive fields
* logs
* storage
* backups
* data exposure

Protect user trust.

---

# Step 6: Secret Review

Search for:

* hardcoded credentials
* exposed tokens
* unsafe configuration

Secrets represent access.

---

# Step 7: Dependency Review

Review:

* unnecessary dependencies
* vulnerable packages
* outdated libraries

Third-party code carries risk.

---

# Step 8: Database Security Review

Check:

* unsafe queries
* permissions
* data leaks
* migrations

Protect stored information.

---

# Step 9: Infrastructure Review

Review:

* environments
* deployments
* access control
* configuration

Production security matters.

---

# Risk Priority

Classify findings.

---

# Critical

Immediate security impact.

Examples:

* authentication bypass
* exposed credentials
* data leaks

---

# High

Important weaknesses.

Examples:

* missing authorization
* unsafe sensitive operations

---

# Medium

Should improve.

Examples:

* missing protections
* risky patterns

---

# Low

Hardening improvements.

---

# Avoid Security Theater

Do not recommend:

* unnecessary tools
* excessive complexity
* unrealistic protections

Security must solve real risks.

---

# Fix Strategy

Prefer:

targeted fix

over:

large rewrite

Security changes should be safe.

---

# Testing Recommendations

Suggest tests for:

* access control
* invalid requests
* sensitive workflows

---

# AI Security Rule

Claude must:

* explain vulnerability
* explain impact
* suggest practical fix

Do not only say something is insecure.

---

# Must Avoid

Never:

* replace complete auth systems unnecessarily
* hide useful errors blindly
* add tools without reason
* ignore project constraints

---

# Output Format

Return:

## Security Summary

Current state.

## Critical Risks

Immediate fixes.

## High Priority

Important improvements.

## Recommendations

Practical changes.

## What Is Already Good

Keep existing protections.

---

# Final Principle

Security review should make systems safer.

Not just more complicated.