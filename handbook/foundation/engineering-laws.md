# Engineering Laws

Engineering laws define rules that should not be violated without a clear technical reason.

Preferences can change.

Frameworks can change.

These laws remain.

---

# Law 1: Existing Code Has Priority

A working production system contains knowledge.

Never rewrite existing code only because another style looks better.

Before changing architecture:

Understand:

* current design
* business requirements
* historical constraints
* dependencies
* risks

Existing patterns should be followed unless there is a proven reason to change.

Valid reasons include:

* security problems
* production risks
* scalability limits
* maintainability issues
* approved migrations

Preference is not a reason for rewriting.

---

# Law 2: Solve The Actual Problem

Never solve problems that do not exist.

Avoid building for:

* imaginary scale
* unknown future requirements
* unlikely scenarios

Solve today's problem while keeping future changes possible.

---

# Law 3: Simplicity Is A Requirement

Simple is not optional.

Every solution must optimize for:

* understanding
* debugging
* maintenance
* operation

A complex solution must prove why complexity is necessary.

---

# Law 4: Code Ownership Never Ends

Writing code creates responsibility.

Before adding code ask:

Can this be:

* maintained?
* debugged?
* tested?
* replaced?

If ownership is unclear, reconsider the solution.

---

# Law 5: Do Not Hide Complexity

Complexity cannot disappear.

It can only move.

Avoid hiding complexity behind:

* unnecessary abstractions
* unclear frameworks
* magic behavior
* excessive automation

Make important behavior visible.

---

# Law 6: Architecture Follows Requirements

Architecture is a response to problems.

Never start with:

* microservices
* distributed systems
* event-driven architecture
* complex patterns

Start with:

* clear modules
* clean boundaries
* simple communication

Increase complexity only when requirements demand it.

---

# Law 7: Every Dependency Has A Cost

Dependencies are borrowed responsibility.

Every dependency introduces:

* security risks
* updates
* compatibility issues
* maintenance overhead

Use dependencies intentionally.

Never add dependencies casually.

---

# Law 8: Security Cannot Be Added Later

Security is part of design.

Every system must protect:

* users
* data
* credentials
* infrastructure

Security shortcuts become future incidents.

---

# Law 9: Data Integrity Comes First

Incorrect data damages systems permanently.

Protect data using:

* validation
* constraints
* transactions
* migrations

Performance improvements must not sacrifice correctness.

---

# Law 10: Failures Must Be Visible

Silent failures create dangerous systems.

Every failure should:

* provide context
* create visibility
* support debugging

Never ignore errors without a reason.

---

# Law 11: Optimization Requires Evidence

Performance work requires measurement.

Never optimize because something feels slow.

First:

Measure.

Identify.

Improve.

Verify.

---

# Law 12: Consistency Beats Personal Preference

A consistent codebase is easier to maintain than a personally preferred one.

Follow existing:

* naming
* structure
* patterns
* conventions

Consistency reduces cognitive load.

---

# Law 13: Abstractions Must Earn Their Place

Do not create abstractions because something might change.

Create abstractions when:

* duplication creates problems
* behavior needs separation
* complexity needs management

Wrong abstractions are worse than duplication.

---

# Law 14: Tests Protect Behavior

Tests exist to verify system behavior.

Focus on:

* important workflows
* business rules
* integrations
* failures

Coverage numbers do not guarantee quality.

---

# Law 15: Production Defines Reality

Development environments are not reality.

Production needs:

* monitoring
* logging
* recovery
* security
* maintainability

A solution is incomplete until it can operate safely.

---

# Law 16: Smaller Changes Win

Large changes increase risk.

Prefer:

* small improvements
* incremental migration
* focused commits

Evolution beats replacement.

---

# Final Law

Never ask:

"Can we build this?"

Always ask:

"Should we build this?"