# Error Handling

Errors are expected parts of software systems.

A reliable system does not avoid every failure.

A reliable system handles failures correctly.

---

# Error Handling Philosophy

Good error handling should:

* make failures visible
* provide useful context
* protect sensitive information
* allow recovery when possible

Errors should never create confusion.

---

# Never Ignore Failures

Do not hide errors silently.

Avoid:

try:
process()

except:
pass

Silent failures create unknown system states.

---

# Existing Project Rule

Existing error handling patterns have priority.

When modifying systems:

Follow current:

* exception style
* response format
* logging approach

Do not introduce a new error strategy without migration.

---

# Fail Clearly

When something fails:

The system should answer:

* what failed?
* where did it fail?
* why did it fail?
* what was affected?

Unclear failures increase recovery time.

---

# Error Boundaries

Handle errors at proper boundaries.

Example:

Database

↓

Business Logic

↓

API Layer

Each layer handles what it understands.

---

# Internal Errors vs User Errors

Separate expected errors from system failures.

User errors:

* invalid input
* missing permissions
* unavailable resources

System errors:

* database failure
* unexpected exception
* infrastructure problems

They require different handling.

---

# Do Not Leak Internals

Never expose:

* stack traces
* database errors
* secrets
* infrastructure details

to users.

Internal details belong in logs.

Not responses.

---

# Error Messages

Good user-facing errors:

* are understandable
* explain the problem
* suggest correction when possible

Example:

"Email address is already registered."

Bad:

"UniqueConstraintViolation users_email_key"

---

# Exception Usage

Use exceptions for exceptional situations.

Avoid using exceptions for normal control flow.

Good:

Payment provider unavailable.

Bad:

Using exceptions to exit normal loops.

---

# Custom Exceptions

Create custom exceptions when they improve meaning.

Good:

PaymentFailed

InvalidOrderState

PermissionDenied

Avoid:

creating custom exceptions for everything.

---

# Logging Errors

Errors should include useful context.

Include:

* operation
* identifier when safe
* failure reason
* relevant metadata

Never log:

* passwords
* tokens
* sensitive data

---

# External Service Failures

External systems fail.

Always handle:

* timeouts
* unavailable services
* invalid responses
* rate limits

Do not assume success.

---

# Retry Handling

Retries should be intentional.

Consider:

* retry limits
* delay strategy
* duplicate execution risk

Never retry forever.

---

# Transaction Failures

Protect data consistency.

When failures happen:

Ensure:

* partial changes are handled
* invalid states are avoided
* rollback behavior is understood

---

# Background Job Errors

Background failures must be visible.

Track:

* failed jobs
* retry attempts
* permanent failures

Invisible background failures damage systems.

---

# Error Recovery

Not every error should stop the system.

Consider:

* fallback behavior
* graceful degradation
* retry options

Recover when safe.

Fail when necessary.

---

# Unexpected Errors

Unexpected failures should:

* be logged
* return safe responses
* alert when critical

Never expose raw failures.

---

# Testing Errors

Test:

* failure scenarios
* invalid inputs
* unavailable dependencies
* permission failures

Happy paths are not enough.

---

# Error Handling Warning Signs

Review when:

* exceptions disappear
* errors are impossible to debug
* logs contain no context
* users see internal messages
* failures corrupt data

---

# Error Handling Checklist

Before completing:

[ ] Failures are visible

[ ] Sensitive data is protected

[ ] Logs provide context

[ ] Users receive safe messages

[ ] Recovery behavior is defined

---

# Final Principle

Good systems are not systems that never fail.

Good systems fail predictably and recover safely.