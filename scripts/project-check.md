# Project Check Script

Analyze project health before making changes.

Inspection comes before modification.

---

# Purpose

Provide automated checks for:

* structure
* configuration
* security risks
* maintainability

---

# Principle

A project check should answer:

What exists?

What works?

What needs attention?

Not:

How can everything be replaced?

---

# Check 1: Project Structure

Review:

* folders
* modules
* organization
* framework conventions

Compare with project type.

---

# Validate

Look for:

* clear responsibilities
* predictable organization
* understandable layout

---

# Avoid Flagging

Do not mark as wrong only because:

* another style exists
* structure is different

Context matters.

---

# Check 2: Technology Stack

Identify:

* language
* framework
* database
* infrastructure

Understand before suggesting.

---

# Check 3: Dependencies

Review:

* dependency list
* unused packages
* outdated packages
* unnecessary complexity

---

# Check 4: Configuration

Verify:

* environment usage
* settings organization
* secret handling

---

# Check 5: Security Basics

Review:

* exposed secrets
* authentication approach
* authorization checks
* sensitive data handling

---

# Check 6: Database

Review:

* models
* migrations
* indexes
* query patterns

---

# Check 7: API Design

Check:

* routes
* validation
* responses
* errors

---

# Check 8: Documentation

Look for:

* README
* setup instructions
* important decisions

Documentation should help.

---

# Check 9: Testing

Review:

* existing tests
* important coverage
* critical workflows

Avoid coverage obsession.

---

# Output Format

Return:

## Project Summary

Detected stack and structure.

## Healthy Areas

Things working well.

## Issues Found

Important concerns.

## Recommendations

Prioritized improvements.

## Do Not Change

Existing good decisions.

---

# AI Rule

Claude must not automatically fix issues after scanning.

Report first.

Modify only when requested.

---

# Final Principle

A good project scan creates understanding.

Understanding creates better changes.