# Async Programming

Asynchronous programming helps systems handle waiting efficiently.

It is a tool.

It is not automatically better than synchronous code.

---

# Async Philosophy

Use async because the workload benefits from it.

Not because async looks modern.

Good engineering chooses the right execution model.

---

# Existing Project Rule

Existing execution style has priority.

When modifying projects:

Respect current:

* synchronous patterns
* asynchronous patterns
* libraries
* framework conventions

Do not convert systems to async without reason.

---

# When To Use Async

Async works well for waiting operations.

Examples:

* network requests
* external API calls
* database drivers supporting async
* file operations
* concurrent I/O

Async helps when time is spent waiting.

---

# When Not To Use Async

Avoid async for:

* simple applications
* CPU-heavy processing
* unnecessary complexity

Async does not automatically make code faster.

---

# CPU Bound Work

Async does not solve CPU bottlenecks.

For CPU-heavy tasks consider:

* optimization
* multiprocessing
* background workers
* specialized systems

Choose based on measurement.

---

# Do Not Mix Randomly

Avoid mixing sync and async without understanding.

Problems:

* blocking event loops
* unexpected performance issues
* confusing code flow

Execution models should be intentional.

---

# Blocking Operations

Inside async code avoid:

* blocking network calls
* blocking database clients
* long synchronous operations

Blocking defeats async benefits.

---

# Async Libraries

Use compatible libraries.

Example:

Async application

*

Blocking HTTP client

can create performance problems.

Choose dependencies carefully.

---

# Concurrency Control

More concurrency is not always better.

Protect systems using:

* limits
* timeouts
* resource control

Unlimited concurrency creates failures.

---

# Timeouts

Async operations should define timeouts.

Especially:

* external APIs
* network calls
* third-party services

Never wait forever.

---

# Error Handling

Async failures must be handled.

Consider:

* failed tasks
* cancellations
* retries
* partial completion

Background failures should not disappear.

---

# Task Management

Avoid creating uncontrolled background tasks.

Every task needs:

* ownership
* lifecycle
* error handling

Fire-and-forget can become fail-and-forget.

---

# Async APIs

Async endpoints should remain simple.

Do not make every function async automatically.

Use async where the execution path benefits.

---

# Database Usage

Async databases require:

* async drivers
* correct connection handling
* proper session management

Async application with blocking database access loses benefits.

---

# Background Jobs vs Async

Async and background jobs solve different problems.

Async:

Handle waiting efficiently.

Background jobs:

Move work outside request flow.

Choose correctly.

---

# Testing Async Code

Test:

* successful execution
* failures
* timeout behavior
* concurrent scenarios when needed

Async bugs can be difficult to reproduce.

---

# Debugging

Async systems require visibility.

Maintain:

* logs
* error tracking
* monitoring

Concurrent execution makes debugging harder.

---

# Avoid Async Over Engineering

Do not convert:

def calculate_total()

into:

async def calculate_total()

without reason.

Async adds complexity.

---

# Async Review Checklist

Before using async:

[ ] Is the operation I/O bound?

[ ] Are libraries async compatible?

[ ] Are failures handled?

[ ] Are timeouts configured?

[ ] Does async simplify the solution?

---

# Warning Signs

Review async usage when:

* everything is async without reason
* blocking calls exist inside async code
* tasks fail silently
* debugging becomes difficult

---

# Final Principle

Async is successful when it makes systems more efficient without making them harder to understand.

Use async because you need it.

Not because you can.