# Service Layer

A service layer exists to organize business operations.

It should simplify the system.

It should not create unnecessary indirection.

---

# Service Layer Philosophy

Services exist to manage:

* business workflows
* coordination
* reusable operations
* complex processes

A service is not required for every function.

A service should have a reason.

---

# Existing Project Rule

Existing service patterns have priority.

When modifying existing projects:

Follow current:

* service organization
* naming style
* dependency flow
* business patterns

Do not introduce service layers into projects that intentionally do not use them.

---

# When To Create A Service

Create services when logic involves:

* multiple steps
* multiple models
* external systems
* transactions
* reusable business workflows

Example:

Order creation:

* validate inventory
* create order
* process payment
* send notification

This belongs in a service.

---

# When Not To Create A Service

Avoid services that only forward calls.

Bad:

UserService.get_user()

calls:

UserRepository.get_user()

calls:

Database.get_user()

without adding behavior.

This creates navigation without value.

---

# Services Are Not Storage Wrappers

A service should represent actions.

Good:

CreateInvoice()

ProcessPayment()

RegisterUser()

Less useful:

GetUser()

UpdateField()

unless additional rules exist.

---

# Business Ownership

Services should contain application decisions.

Examples:

* when something happens
* which rules apply
* how workflows execute

Business decisions should be visible.

---

# Framework Independence

Services should avoid depending directly on:

* HTTP requests
* controllers
* views
* framework objects

This keeps logic easier to:

* test
* reuse
* understand

---

# Service Size

A service should have a focused responsibility.

Avoid:

UserService containing:

* authentication
* billing
* notifications
* reporting

Split because responsibilities differ.

Not because files are large.

---

# Dependency Rules

Services may depend on:

* data access
* integrations
* utilities
* other domain services when needed

Avoid:

* circular dependencies
* unclear ownership
* deep dependency chains

---

# Transaction Management

Services are often responsible for workflows requiring consistency.

Example:

Create order:

Start transaction

Create records

Update inventory

Commit

Keep transaction boundaries understandable.

---

# External Integrations

Services can coordinate external systems.

Handle:

* failures
* retries
* timeouts
* unexpected responses

Never assume external systems always work.

---

# Service Naming

Name services based on responsibility.

Good:

PaymentProcessor

ReportGenerator

NotificationService

Avoid unclear names:

CommonService

HelperService

UtilityService

Names should communicate ownership.

---

# Reuse Rule

Do not create services for imaginary reuse.

Create reusable components after:

* duplication appears
* patterns are understood
* abstraction becomes obvious

Wrong abstraction costs more than duplication.

---

# Testing Services

Services should be easy to test.

Focus tests on:

* business decisions
* workflow behavior
* failure handling

Avoid testing internal implementation details.

---

# Service Warning Signs

Review services when:

* every method simply calls another layer
* finding logic requires opening many files
* services depend on everything
* responsibilities are unclear

Services should reduce complexity.

---

# Service Review Checklist

Before creating a service ask:

1. What business responsibility does it own?
2. Does it reduce complexity?
3. Is logic reused?
4. Does it coordinate multiple operations?
5. Would direct implementation be simpler?

---

# Final Principle

A good service layer makes business behavior easier to understand.

A bad service layer hides simple code behind more files.