# Logging

Logs explain what happened inside a system.

Good logs help investigate problems.

Bad logs create noise.

---

# Logging Philosophy

Logs should provide:

* visibility
* debugging information
* operational understanding

Log useful information.

Not everything.

---

# Existing Project Rule

Existing logging strategy has priority.

Before changing:

Understand:

* log format
* monitoring tools
* production requirements

Do not replace logging systems unnecessarily.

---

# Purpose Of Logs

Logs should help answer:

What happened?

When did it happen?

Where did it happen?

Why did it fail?

---

# Log Levels

Use levels correctly.

---

# DEBUG

Development details.

Examples:

* internal flow
* temporary debugging
* detailed information

Avoid excessive production debug logs.

---

# INFO

Expected important events.

Examples:

* service started
* scheduled task completed
* important workflow finished

---

# WARNING

Unexpected but recoverable situations.

Examples:

* retry required
* fallback used
* slow response detected

---

# ERROR

Failures requiring attention.

Examples:

* failed operations
* external service errors
* unexpected exceptions

---

# CRITICAL

Severe system failures.

Examples:

* application unavailable
* major infrastructure failure

---

# Avoid Print Debugging

Avoid:

print()

for application logging.

Use proper logging tools.

Logs need:

* levels
* formatting
* destinations

---

# Structured Logging

Prefer structured logs when useful.

Example fields:

* timestamp
* request id
* user context
* operation
* status

Machines should understand logs.

---

# Request Tracking

Production systems benefit from:

request IDs

correlation IDs

They connect related events.

---

# Error Logging

Errors should include:

* what failed
* where it failed
* useful context

Without exposing sensitive data.

---

# Sensitive Data

Never log:

* passwords
* tokens
* API keys
* secrets
* private information

Logs are stored data.

Protect them.

---

# External Services

Log external failures.

Include:

* service name
* failure reason
* retry behavior

Avoid leaking credentials.

---

# Background Jobs

Log important job events:

* start
* completion
* failure
* retries

Background should not mean invisible.

---

# Database Logging

Useful:

* slow queries
* failures
* connection issues

Avoid logging sensitive query data.

---

# Log Volume

Too many logs hide problems.

Avoid:

logging every small action

without purpose.

---

# Log Retention

Production logs need:

* storage planning
* retention rules
* access control

---

# User Actions

Audit important actions when required.

Examples:

* permission changes
* financial operations
* security events

---

# Monitoring Integration

Logs should work with:

* alerting
* dashboards
* error tracking

Logs are part of observability.

---

# Testing Logs

Critical logging behavior can be tested.

Especially:

* security logs
* audit trails

---

# Warning Signs

Review logging when:

* debugging production is impossible
* logs expose secrets
* errors disappear silently
* logs are ignored because of noise

---

# Logging Checklist

Before completion:

[ ] Important events logged

[ ] Errors have context

[ ] Sensitive data protected

[ ] Log levels used correctly

[ ] Noise avoided

---

# Final Principle

Good logs tell the story of a system.

Write logs for the engineer solving tomorrow's problem.