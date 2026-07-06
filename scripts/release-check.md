# Release Check Script

Validate readiness before releasing changes.

A release should be controlled.

Not hopeful.

---

# Purpose

Verify:

* code quality
* configuration
* security
* database safety
* deployment readiness

before production changes.

---

# Principle

Successful deployment means:

Application works correctly.

Not only:

Deployment command succeeded.

---

# Step 1: Review Changes

Understand:

What changed?

Why changed?

What systems are affected?

---

# Step 2: Quality Validation

Run existing checks:

* formatting
* linting
* tests
* build verification

Use project standards.

---

# Step 3: Test Verification

Confirm important workflows.

Prioritize:

* business operations
* authentication
* payments
* critical APIs

---

# Step 4: Security Verification

Check:

* secrets
* authentication changes
* authorization changes
* sensitive data handling

Do not release exposed risks.

---

# Step 5: Configuration Verification

Validate:

* environment variables
* feature flags
* service configuration

Configuration problems are release problems.

---

# Step 6: Dependency Verification

Review:

* new dependencies
* version updates
* compatibility changes

Unexpected dependency changes create risk.

---

# Step 7: Database Verification

For database changes:

Check:

* migrations
* existing data impact
* rollback considerations

Protect production data.

---

# Step 8: Infrastructure Verification

Review:

* deployment configuration
* resources
* networking
* external services

---

# Step 9: Documentation Verification

Update documentation when:

* setup changes
* APIs change
* operations change

---

# Step 10: Rollback Readiness

Before releasing know:

How do we recover?

Prepare before problems happen.

---

# Deployment Validation

After deployment:

Check:

* application health
* logs
* important workflows
* errors

---

# Monitoring

Watch:

* failures
* performance
* unexpected behavior

A release continues after deployment.

---

# Failed Release

If issues appear:

Prioritize:

restore stability

Then investigate.

---

# Release Notes

When needed include:

* changes
* migration notes
* operational impact

---

# Emergency Releases

Hotfix rules:

* minimal changes
* solve immediate issue
* review afterward

---

# AI Behavior Rule

Claude must consider:

* production impact
* compatibility
* recovery

before release recommendations.

---

# Avoid

Never release:

* unknown changes
* untested critical paths
* exposed secrets
* unsafe migrations

---

# Output Format

Return:

## Release Summary

What is changing.

## Verification

Checks completed.

## Risks

Known concerns.

## Deployment Notes

Important steps.

## Rollback Plan

Recovery approach.

---

# Final Principle

Production confidence comes from preparation.

Reliable releases are engineered.