# Deployment

Deployment is the process of safely delivering software to users.

A successful deployment is predictable, repeatable and recoverable.

---

# Deployment Philosophy

Good deployment focuses on:

* reliability
* repeatability
* visibility
* recovery

Deployments should be boring.

Surprising deployments are dangerous.

---

# Existing System Rule

Existing deployment strategy has priority.

Before changing:

Understand:

* hosting environment
* release process
* infrastructure
* constraints

Do not replace working deployments unnecessarily.

---

# Repeatable Deployments

Deployment steps should be automated when possible.

Avoid:

manual commands

unknown server changes

undocumented fixes

The same input should create the same result.

---

# Environment Separation

Maintain separate environments when needed.

Examples:

Development

Staging

Production

Production should not be used for testing.

---

# Configuration

Applications should change behavior through configuration.

Not code changes.

Examples:

DATABASE_URL

API_KEYS

FEATURE_FLAGS

---

# Secrets

Never store secrets in:

* source code
* repositories
* documentation

Use secure secret management.

---

# Build Process

Builds should be:

* predictable
* versioned
* reproducible

Avoid depending on unknown machine state.

---

# Deployment Validation

Before production:

Verify:

* tests pass
* migrations reviewed
* configuration exists
* dependencies are correct

---

# Database Changes

Deploy database changes carefully.

Consider:

* migration order
* compatibility
* rollback impact

Database changes are high risk.

---

# Rollback Strategy

Before deployment ask:

"What happens if this fails?"

Have a recovery approach.

---

# Zero Downtime

Not every system requires zero downtime.

Choose based on:

* users
* business needs
* system requirements

Do not add unnecessary complexity.

---

# Health Checks

Production applications should expose health information.

Examples:

* application running
* dependencies available
* critical services healthy

---

# Logging

Deployment should maintain:

* application logs
* error visibility
* operational information

Do not deploy blind.

---

# Monitoring

Production needs visibility.

Track:

* failures
* availability
* performance

Problems should be discovered quickly.

---

# Version Control

Deploy known versions.

Track:

* commit
* release
* build artifact

Know what is running.

---

# Manual Server Changes

Avoid modifying production servers manually.

If manual changes happen:

Document them.

Automate later if repeated.

---

# Dependencies

Production dependencies should be controlled.

Avoid:

install latest during deployment

Unexpected updates create failures.

---

# Background Workers

Deploy workers carefully.

Consider:

* queue compatibility
* running tasks
* version mismatch

---

# Scheduled Jobs

Document:

* what runs
* when it runs
* ownership

Hidden jobs create surprises.

---

# Scaling

Scale based on real demand.

Order:

1. Fix problems

2. Optimize

3. Add resources

4. Add architecture complexity

---

# Deployment Security

Production deployments require:

* restricted access
* protected credentials
* secure communication

Convenience should not remove safety.

---

# Warning Signs

Review deployment when:

* only one person can deploy
* deployments regularly fail
* fixes happen directly on servers
* rollback is impossible

---

# Deployment Checklist

Before deploying:

[ ] Code version known

[ ] Tests completed

[ ] Configuration verified

[ ] Secrets protected

[ ] Migration impact reviewed

[ ] Recovery plan exists

---

# Final Principle

A great deployment is forgettable.

Reliable systems make releases routine.