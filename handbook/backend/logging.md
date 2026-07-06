# Logging

Logs exist to understand system behavior.

Good logs help engineers debug, monitor and operate production systems.

Logs are not random messages.

They are operational information.

---

# Logging Philosophy

Logging should answer:

What happened?

Where did it happen?

Why did it happen?

What context helps investigation?

Logs should reduce debugging time.

---

# Existing Project Rule

Existing logging patterns have priority.

When modifying systems:

Follow current:

* logging library
* log format
* naming conventions
* severity usage

Do not introduce new logging systems unnecessarily.

---

# Logging Is Not Debugging

Temporary debugging:

print(value)

Production logging:

logger.info(
"Payment processed",
extra=context
)

Remove temporary debugging before completion.

---

# Log Levels

Use levels intentionally.

---

## DEBUG

Detailed information for development.

Examples:

* execution flow
* temporary investigation details
* detailed diagnostics

Avoid excessive production debug logs.

---

## INFO

Important normal events.

Examples:

* service started
* scheduled task completed
* important workflow finished

Do not log every small action.

---

## WARNING

Unexpected but recoverable situations.

Examples:

* retry required
* external service delay
* fallback used

System continues working.

---

## ERROR

Operation failed.

Examples:

* request failure
* database error
* external integration failure

Requires investigation.

---

## CRITICAL

System-level failures.

Examples:

* service unavailable
* data corruption risk
* major outage

Requires immediate attention.

---

# Useful Context

Logs should include useful metadata.

Examples:

* operation name
* request identifier
* user identifier when safe
* resource identifier
* execution status

Context makes debugging possible.

---

# Sensitive Information

Never log:

* passwords
* authentication tokens
* secret keys
* private credentials
* sensitive personal data

Logs are not secure storage.

---

# Error Logging

When logging errors:

Include:

* what failed
* relevant context
* exception details internally

Avoid:

* hiding errors
* duplicate logging everywhere
* losing stack information

---

# Avoid Log Noise

More logs do not mean better visibility.

Avoid:

* logging every function call
* meaningless success messages
* duplicate logs

Noise hides important signals.

---

# Structured Logging

Prefer structured logs when possible.

Good:

{
"event": "payment_failed",
"order_id": "123",
"reason": "timeout"
}

Better for searching and monitoring.

---

# Request Logging

Important request information:

* endpoint
* status
* duration
* failure reason

Avoid storing:

* sensitive payloads
* credentials

---

# External Service Logging

For external calls track:

* service name
* success/failure
* response time
* error reason

External failures should be visible.

---

# Background Job Logging

Background jobs should log:

* start
* completion
* failures
* retries

Silent job failures are dangerous.

---

# Performance Logging

Add performance logs when:

* operations are expensive
* bottlenecks are investigated
* monitoring is required

Do not add unnecessary timing everywhere.

---

# Audit Logging

Audit logs are different from application logs.

Use audit logs for:

* important user actions
* security events
* sensitive changes

Keep them reliable.

---

# Logging And Monitoring

Logs should support:

* debugging
* alerts
* incident investigation

A production system should explain itself.

---

# Logging Review

Before adding a log ask:

1. Will this help during an incident?
2. Does it provide useful context?
3. Is the information safe?
4. Will this create noise?

---

# Warning Signs

Review logging when:

* production issues require guessing
* logs expose secrets
* logs are ignored because of noise
* failures leave no evidence

---

# Logging Checklist

Before completion:

[ ] Important failures are logged

[ ] Context exists

[ ] Sensitive data is protected

[ ] Log level is correct

[ ] Noise is avoided

---

# Final Principle

Good logs tell the story of a system.

They help future engineers understand what happened without guessing.