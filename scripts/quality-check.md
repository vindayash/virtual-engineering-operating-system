# Quality Check Script

Validate project quality before changes are released.

Quality checks should prevent problems.

Not create unnecessary friction.

---

# Purpose

Review:

* correctness
* consistency
* maintainability
* security basics

using project standards.

---

# Principle

Quality is not about perfect scores.

Quality means the system remains safe to change.

---

# Step 1: Detect Existing Tools

Before adding anything:

Find existing:

* linters
* formatters
* test tools
* CI checks

Use current workflow.

---

# Step 2: Formatting Check

Verify consistent formatting.

Use project tools.

Examples:

* language formatter
* framework conventions

Avoid style arguments.

---

# Step 3: Linting Check

Detect:

* possible bugs
* unused code
* risky patterns

Focus on useful warnings.

---

# Step 4: Type Checking

Use when project supports it.

Check:

* incorrect assumptions
* unsafe usage
* integration issues

---

# Step 5: Test Execution

Run existing tests.

Prioritize:

* important workflows
* business logic
* security behavior

---

# Step 6: Security Review

Check:

* secrets exposure
* unsafe patterns
* dependency warnings
* configuration mistakes

---

# Step 7: Documentation Check

Verify important documentation exists.

Examples:

* setup
* architecture decisions
* operational notes

---

# Step 8: Configuration Check

Validate:

* required settings
* environment usage
* missing configuration

---

# Code Review Signals

Highlight:

* duplicated risky logic
* unclear responsibilities
* overly complex areas

---

# Avoid False Improvements

Do not fail quality because:

* another style exists
* personal preference differs
* newer tool exists

---

# Adding Tools

Only suggest new tools when:

* clear problem exists
* benefit is meaningful
* maintenance cost is acceptable

---

# Existing Project Rule

Follow existing:

* style
* configuration
* pipelines

Consistency wins.

---

# AI Behavior Rule

Claude should:

* report findings
* explain impact
* suggest fixes

Do not rewrite automatically.

---

# Avoid

Never automatically:

* reformat entire repositories
* replace tooling
* enforce unrelated standards
* add unnecessary checks

---

# Output Format

Return:

## Checks Performed

What was reviewed.

## Passed

Healthy areas.

## Issues

Problems found.

## Recommendations

Prioritized fixes.

---

# Final Principle

Quality checks should increase confidence.

Not slow development without reason.