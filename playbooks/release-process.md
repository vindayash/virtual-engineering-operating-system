# Playbook: Release Process

Releases move changes into real environments.

A good release is predictable.

Not stressful.

---

# Purpose

Deploy software safely while protecting:

* users
* data
* system reliability

---

# Active Agents

Use:

* Backend Agent
* Database Agent
* Security Agent
* Reviewer Agent

---

# Primary Rule

A release should be:

planned

verified

recoverable

Do not rely on luck.

---

# Step 1: Understand Release Scope

Identify:

What changed?

Examples:

* features
* bug fixes
* database changes
* infrastructure updates

---

# Step 2: Review Changes

Check:

* code impact
* dependencies
* configuration
* compatibility

Understand what is being deployed.

---

# Step 3: Verify Tests

Run relevant:

* automated tests
* manual checks
* critical workflows

Confidence matters.

---

# Step 4: Security Check

Review:

* secrets
* permissions
* authentication changes
* sensitive data handling

Security issues should not reach production.

---

# Step 5: Database Review

For database changes:

Confirm:

* migrations
* data impact
* compatibility
* rollback considerations

---

# Step 6: Configuration Review

Verify:

* environment variables
* feature flags
* service configuration

Configuration is part of release.

---

# Step 7: Dependency Review

Check:

* new packages
* version changes
* security updates

Dependencies affect production.

---

# Step 8: Deployment

Deploy using existing process.

Respect:

* CI/CD workflow
* infrastructure rules
* team practices

---

# Migration Execution

For migrations:

Monitor:

* execution time
* errors
* application compatibility

---

# Step 9: Post Release Verification

After deployment:

Check:

* application health
* important flows
* logs
* errors

Deployment success does not mean application success.

---

# Monitoring

Watch:

* error rate
* performance
* system behavior

Confirm stability.

---

# Rollback Planning

Before release know:

How do we recover?

Rollback should not be invented during failure.

---

# Failed Release

If problems happen:

Prioritize:

restore stability

Then investigate.

---

# Documentation Updates

Update when release changes:

* setup
* APIs
* operations
* architecture

---

# Release Notes

When useful document:

* changes
* migration requirements
* important impacts

---

# Avoid Large Risky Releases

Prefer:

smaller releases

over:

huge unpredictable deployments

---

# Emergency Releases

Hotfixes should:

* solve immediate problem
* minimize changes
* receive follow-up review

---

# AI Behavior Rule

Claude must consider:

* deployment impact
* compatibility
* rollback

before release changes.

---

# Avoid

Never:

* deploy unknown changes
* ignore failing checks
* mix unrelated changes
* skip security considerations

---

# Release Checklist

Before production:

[ ] Changes understood

[ ] Tests verified

[ ] Configuration checked

[ ] Database safe

[ ] Rollback considered

[ ] Monitoring ready

---

# Final Principle

A good release should be repeatable.

Confidence comes from preparation.