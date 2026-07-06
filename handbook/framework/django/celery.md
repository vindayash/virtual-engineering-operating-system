# Django Celery

Celery handles background and asynchronous processing.

It should solve real execution problems.

It should not be added automatically.

---

# Celery Philosophy

Celery exists to move work outside the request lifecycle.

Use Celery to improve:

* reliability
* user experience
* processing capability

Not because async architecture looks better.

---

# Existing Project Rule

Existing background processing has priority.

Before changing:

Understand:

* current workers
* queues
* scheduled tasks
* retry behavior

Do not replace working systems unnecessarily.

---

# When To Use Celery

Use Celery for:

* long-running tasks
* retryable operations
* scheduled jobs
* external integrations
* heavy processing

Examples:

* sending emails
* generating reports
* processing files
* syncing third-party systems

---

# When Not To Use Celery

Avoid Celery for:

* simple fast operations
* unnecessary separation
* hiding inefficient code

A background task should solve a real problem.

---

# Request Flow

Good:

Request

↓

Save required data

↓

Queue task

↓

Return response

↓

Worker processes task

Users should not wait unnecessarily.

---

# Task Location

Standard:

apps/

└── users/

```
├── tasks.py
```

Tasks should live close to their domain.

---

# Task Responsibility

Tasks should have one clear purpose.

Good:

send_invoice_email()

generate_monthly_report()

Bad:

process_everything()

---

# Keep Business Logic Out Of Tasks

Tasks execute workflows.

They should not own all business rules.

Prefer:

Task

↓

Service

↓

Models

---

# Example

Good:

@shared_task

def send_email_task(user_id):

```
notification_service.send_email(user_id)
```

Task handles execution.

Service handles behavior.

---

# Idempotency

Tasks should handle repeated execution safely.

Celery tasks can run more than once.

Example:

Avoid:

charging payment twice

sending duplicate critical actions

---

# Retry Handling

Retries must be intentional.

Define:

* retry limits
* delay strategy
* failure handling

Never retry forever.

---

# External APIs

Celery works well with unreliable services.

Handle:

* timeouts
* failures
* rate limits
* unavailable systems

External systems fail.

---

# Transactions

Be careful when triggering tasks after database writes.

Avoid:

Task starts

before

transaction commits

Use transaction-safe patterns.

---

# Scheduled Tasks

Use scheduled tasks for:

* cleanup jobs
* reports
* synchronization

Document what runs and when.

---

# Queue Separation

Separate queues when needed.

Examples:

* high priority jobs
* slow processing
* heavy workloads

Do not create many queues without reason.

---

# Monitoring

Production Celery requires:

* failure visibility
* worker monitoring
* queue tracking

Background does not mean invisible.

---

# Logging

Tasks should log:

* important execution
* failures
* retry events

Avoid logging sensitive data.

---

# Performance

Moving slow code into Celery does not fix bad code.

Optimize when needed.

Background processing only changes when work happens.

---

# Testing Tasks

Test:

* task behavior
* service logic
* failures
* retries

Do not ignore async code.

---

# Warning Signs

Review Celery usage when:

* every action becomes a task
* failures disappear
* retries run forever
* business logic only exists in tasks
* workers are impossible to debug

---

# Celery Checklist

Before adding:

[ ] Does this need background execution?

[ ] Is failure handled?

[ ] Are retries safe?

[ ] Is duplicate execution safe?

[ ] Is monitoring available?

---

# Final Principle

Celery moves work.

It does not remove responsibility.

Background systems must be designed as carefully as request systems.