# Dependency Check Script

Review project dependencies for safety, necessity and health.

Dependencies expand what a project trusts.

Every dependency is a long-term commitment.

---

# Purpose

Review:

* necessity
* security
* maintenance
* version health

using project standards.

---

# Principle

The best dependency is often no dependency.

Add only what earns its place.

---

# Step 1: Detect Dependency Sources

Find existing declarations.

Examples:

* requirements.txt
* pyproject.toml
* poetry.lock
* package.json

Use the project's real manifest.

---

# Step 2: Necessity Check

For each dependency ask:

* is it actually used?
* does the framework already solve this?
* could a small amount of code replace it?

Remove unused packages.

---

# Step 3: Security Check

Detect known vulnerabilities.

Examples:

* pip-audit
* npm audit
* safety

Prioritize:

* high severity
* direct dependencies
* internet-facing code

---

# Step 4: Maintenance Check

Review dependency health.

Consider:

* last release date
* open issues
* abandonment signals
* single-maintainer risk

Unmaintained packages become liabilities.

---

# Step 5: Version Check

Identify:

* outdated packages
* pinned versions
* unpinned production dependencies

Prefer intentional, reproducible versions.

---

# Step 6: License Check

Verify licenses are compatible with project use.

Flag:

* restrictive licenses
* missing licenses
* license changes on upgrade

---

# Step 7: Duplication Check

Detect:

* multiple packages solving the same problem
* transitive duplication
* overlapping utilities

Consolidate where safe.

---

# Upgrade Rule

Before upgrading:

Understand:

* breaking changes
* changelog
* impact on existing behavior

Do not blindly update packages.

---

# Existing Project Rule

Follow existing:

* dependency manager
* version strategy
* lock file discipline

Do not switch tooling without reason.

---

# AI Behavior Rule

Claude should:

* report findings
* explain risk
* suggest focused changes

Do not upgrade or remove packages automatically.

---

# Avoid

Never automatically:

* upgrade every package to latest
* remove dependencies without checking usage
* switch package managers
* add packages for trivial problems

---

# Output Format

Return:

## Dependencies Reviewed

What was checked.

## Healthy

Safe and necessary dependencies.

## Issues

Vulnerable, unused or unmaintained packages.

## Recommendations

Prioritized, safe actions.

---

# Final Principle

Dependencies should reduce work.

Not quietly increase risk.
