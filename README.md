# VEOS

VEOS (Virtual Engineering Operating System)

A practical engineering system for building, reviewing and maintaining software projects with AI assistance.

---

# Purpose

VEOS provides consistent engineering behavior.

It helps AI assistants act like experienced engineers by following:

* clear principles
* safe workflows
* practical architecture decisions
* maintainable coding standards

---

# Philosophy

Software engineering is about solving problems.

Not adding unnecessary complexity.

VEOS prioritizes:

1. Understanding before changes

2. Simple solutions first

3. Existing systems before rewrites

4. Security by default

5. Maintainability over cleverness

---

# Core Rule

Before modifying anything:

Understand the system.

Before adding complexity:

Justify the need.

Before replacing:

Respect what exists.

---

# Structure

VEOS contains:

---

## handbook/

Engineering knowledge base.

Defines:

* architecture principles
* backend standards
* database rules
* security practices
* infrastructure guidelines

---

## agents/

Engineering roles.

Defines AI behavior for:

* architects
* backend engineers
* reviewers
* security engineers
* refactoring

---

## commands/

Reusable engineering actions.

Examples:

* analyze project
* create feature
* fix bug
* review code
* optimize performance

---

## playbooks/

Complete workflows.

Examples:

* starting projects
* joining projects
* production issues
* releases

---

## templates/

Reusable project templates.

Examples:

* README
* ADR
* FastAPI
* Django
* Docker

---

## examples/

Reference implementations.

Shows:

good patterns

vs

bad patterns

---

## generators/

Rules for generating:

* projects
* APIs
* models
* tests
* documentation

---

## scripts/

Automation guidance.

Examples:

* quality checks
* dependency checks
* release validation

---

# Engineering Principles

## Simplicity

Choose the simplest solution that satisfies requirements.

---

## Context First

Different projects need different solutions.

Avoid universal answers.

---

## Framework Respect

Use frameworks correctly.

Do not rebuild what they already solve.

---

## Incremental Improvement

Improve existing systems safely.

Avoid unnecessary rewrites.

---

## Security Awareness

Security belongs in normal development.

Not only after completion.

---

## Data Protection

Code can be rewritten.

Data must be protected.

---

# AI Behavior

When using VEOS:

AI should:

* inspect before modifying
* explain reasoning
* preserve existing patterns
* minimize unnecessary changes
* consider security

---

# AI Must Avoid

Never automatically:

* rewrite working projects
* add unnecessary abstractions
* introduce trendy tools
* ignore existing architecture
* optimize without evidence

---

# Recommended Workflow

Existing project:

Analyze

↓

Understand

↓

Plan

↓

Change

↓

Verify

---

New project:

Requirements

↓

Architecture

↓

Implementation

↓

Review

↓

Release

---

# Goal

VEOS does not make AI write more code.

It helps AI write the right code.

---

# Final Principle

Great engineering is not about maximum complexity.

It is about making complexity manageable.


# Using VEOS With Claude

VEOS works by providing Claude with engineering instructions through `CLAUDE.md`.

Claude does not automatically know about VEOS. The project must expose VEOS instructions using one of the following approaches.

---

# Option 1: Add VEOS Inside Each Project

Recommended for simple usage.

Copy the VEOS folder into your project.

Example:

```text
my-project/
│
├── CLAUDE.md
├── src/
├── tests/
│
└── VEOS/
    ├── CLAUDE.md
    ├── settings.json
    ├── handbook/
    ├── agents/
    ├── commands/
    └── ...
```

Create a root `CLAUDE.md` file:

```md
# Project Instructions

Use VEOS as the engineering operating system.

Load:

./VEOS/CLAUDE.md

Follow:

./VEOS/handbook/
./VEOS/agents/
./VEOS/commands/
./VEOS/playbooks/
./VEOS/templates/
./VEOS/generators/

Priority:

1. Existing project architecture
2. Current requirements
3. VEOS engineering standards

Before changing code:

- analyze existing implementation
- understand project patterns
- follow VEOS workflows
```

Start Claude:

```bash
cd my-project

claude
```

Claude loads the root instructions and applies VEOS.

---

# Option 2: Global VEOS Installation

Recommended for daily development.

Keep one VEOS copy on your machine.

Example:

```text
~/engineering/
└── VEOS/
    ├── CLAUDE.md
    ├── handbook/
    ├── agents/
    └── ...
```

Each project only needs a small `CLAUDE.md`.

Example:

```text
projects/
│
├── api-project/
│   └── CLAUDE.md
│
└── backend-service/
    └── CLAUDE.md
```

Project `CLAUDE.md`:

```md
# Project Instructions

Use VEOS engineering standards.

Load:

~/engineering/VEOS/CLAUDE.md

Apply VEOS rules for:

- architecture decisions
- backend development
- security reviews
- refactoring
- documentation
```

Benefits:

* one VEOS installation
* easy updates
* shared standards across projects

---

# Option 3: Git Submodule

Recommended for teams and version control.

Host VEOS as a Git repository.

Example:

```text
github.com/username/VEOS
```

Add VEOS to any project:

```bash
git submodule add git@github.com:username/VEOS.git VEOS
```

Project structure:

```text
backend-project/
│
├── CLAUDE.md
├── app/
├── tests/
│
└── VEOS/
    ├── CLAUDE.md
    ├── handbook/
    └── ...
```

Root `CLAUDE.md`:

```md
# Project Instructions

Use repository VEOS configuration.

Load:

./VEOS/CLAUDE.md

Follow VEOS workflows before making engineering changes.
```

Benefits:

* version controlled
* team friendly
* update VEOS independently
* consistent engineering standards

---

# Recommended Usage

Personal development:

Use Global Installation.

Individual repositories:

Use Project Copy.

Teams:

Use Git Submodule.

---

# Example Commands

Analyze existing project:

```text
Analyze this repository using VEOS.
```

Create feature:

```text
Create this feature following VEOS standards.
```

Review code:

```text
Review this implementation using VEOS.
```

Fix bug:

```text
Debug and fix this issue using VEOS workflow.
```

Claude will automatically apply the relevant:

* agents
* commands
* playbooks
* templates
* engineering rules