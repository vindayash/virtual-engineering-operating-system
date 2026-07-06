# VEOS Usage Guide

How to use the Virtual Engineering Operating System with AI assistants.

---

# Purpose

VEOS helps AI work as an engineering partner.

It provides:

* engineering standards
* workflows
* generation rules
* review practices

---

# Getting Started

Place VEOS where the AI assistant can access it.

Ensure:

CLAUDE.md

is available as the primary instruction file.

---

# Slash Commands (Claude Code)

VEOS ships runnable slash commands in `.claude/commands/`.

They turn the VEOS workflows into commands you type directly.

---

## Enabling Commands

Claude Code discovers commands in `<project>/.claude/commands/`.

If VEOS lives at your project root:

Commands work automatically.

If VEOS lives in a subfolder (`./VEOS/`):

Copy or symlink the commands into your project:

```bash
mkdir -p .claude/commands
cp VEOS/.claude/commands/veos-*.md .claude/commands/
```

Then restart Claude Code so the commands load.

---

## Available Commands

* `/veos-analyze` — analyze an existing repo before changing it
* `/veos-feature` — build a feature (understand, plan, implement, verify)
* `/veos-fix` — debug and fix a bug safely
* `/veos-review` — impact-based code review
* `/veos-refactor` — refactor while preserving behavior
* `/veos-security` — security review
* `/veos-optimize` — performance work, measured first
* `/veos-docs` — generate useful documentation
* `/veos-deps` — dependency safety and health check
* `/veos-quality` — format, lint, type, test, security pass

---

## Command Usage

Pass context after the command.

Examples:

```text
/veos-analyze
/veos-feature add password reset via email token
/veos-fix 500 on POST /orders when cart is empty
/veos-security the new /admin endpoints
/veos-deps
```

Each command loads the relevant VEOS handbook and workflow files, then applies them to your input.

The `veos-` prefix avoids clashing with Claude Code built-ins like `/review` and `/security-review`.

---

# Recommended Workflow

For every project:

1. Load VEOS

2. Understand project

3. Select workflow

4. Execute changes

5. Verify results

---

# New Project Workflow

Use:

playbooks/new-project.md

Process:

Requirements

↓

Architecture

↓

Implementation

↓

Testing

↓

Release

---

# Existing Project Workflow

Use:

playbooks/existing-project.md

Process:

Analyze

↓

Understand

↓

Plan

↓

Modify

↓

Verify

Never start with rewriting.

---

# Creating Features

Use:

commands/create-feature.md

Expected behavior:

* understand requirement
* follow architecture
* implement safely
* test important paths

---

# Fixing Bugs

Use:

commands/fix-bug.md

Process:

Reproduce

↓

Find cause

↓

Fix

↓

Verify

Do not randomly change code.

---

# Reviewing Code

Use:

commands/review-code.md

Focus:

* bugs
* security
* maintainability
* real risks

Avoid preference-only reviews.

---

# Refactoring Code

Use:

commands/refactor-safe.md

Rules:

* preserve behavior
* small improvements
* no unnecessary rewrites

---

# Security Review

Use:

commands/security-review.md

Check:

* authentication
* authorization
* secrets
* sensitive data

---

# Performance Work

Use:

commands/optimize-performance.md

Rule:

Measure first.

Optimize second.

---

# Generating FastAPI Projects

Use:

generators/fastapi-generator.md

Follow:

templates/fastapi-template.md

---

# Generating Django Projects

Use:

generators/django-generator.md

Follow:

templates/django-template.md

---

# Creating APIs

Use:

generators/api-generator.md

Ensure:

* validation
* permissions
* safe responses

---

# Creating Models

Use:

generators/model-generator.md

Protect:

* data structure
* migrations
* relationships

---

# Creating Tests

Use:

generators/test-generator.md

Test:

important behavior

Not:

random lines

---

# Creating Documentation

Use:

generators/docs-generator.md

Document:

why

not only:

what

---

# Production Issues

Use:

playbooks/production-issue.md

Process:

Impact

↓

Evidence

↓

Fix

↓

Verify

↓

Prevent

---

# Releases

Use:

playbooks/release-process.md

Before release:

* verify tests
* check security
* review database impact
* prepare rollback

---

# Common Commands

Examples:

Analyze repository:

Follow analyze-project command.

Build feature:

Follow create-feature command.

Improve code:

Follow refactor-safe command.

Prepare release:

Follow release workflow.

---

# AI Collaboration Rules

Good prompts:

"Analyze this project using VEOS."

"Create this feature following VEOS."

"Review this code using VEOS."

---

# Expected AI Behavior

AI should:

* explain decisions
* consider tradeoffs
* protect existing systems
* prefer maintainability

---

# AI Should Avoid

Do not ask AI to:

* blindly rewrite
* add complexity without reason
* copy architecture from unrelated projects

---

# Best Results

Provide:

* project context
* constraints
* goals
* existing problems

Better context creates better engineering.

---

# Final Principle

VEOS is not a rulebook for writing more code.

It is a system for making better engineering decisions.