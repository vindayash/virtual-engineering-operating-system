# Setup Project Script

Prepare a project environment safely and consistently.

Setup should be repeatable.

Not based on hidden knowledge.

---

# Purpose

Guide project initialization:

* local environment setup
* dependency installation
* configuration
* verification

---

# Principle

A new developer should be able to run the project using documented steps.

No guessing.

---

# Step 1: Detect Project Type

Identify:

* language
* framework
* package manager
* runtime requirements

Examples:

Python

Node

Docker

---

# Step 2: Verify Requirements

Check required tools.

Examples:

* language version
* package manager
* database
* external services

---

# Step 3: Environment Setup

Create isolated environments when needed.

Examples:

Python:

virtual environment

Node:

package environment

Follow ecosystem standards.

---

# Step 4: Install Dependencies

Use existing project files.

Examples:

requirements.txt

pyproject.toml

package files

Do not randomly upgrade packages.

---

# Step 5: Configuration Setup

Check:

* environment files
* required variables
* configuration templates

Use:

.env.example

Never create real secrets.

---

# Step 6: Database Setup

If required:

Prepare:

* database connection
* migrations
* initial setup

Follow project instructions.

---

# Step 7: External Services

Identify required services.

Examples:

* cache
* storage
* message systems
* APIs

Document requirements.

---

# Step 8: Run Application

Verify:

Application starts successfully.

Record required commands.

---

# Step 9: Run Tests

If tests exist:

Execute them.

Confirm environment works.

---

# Step 10: Validate Setup

Check:

* application running
* dependencies installed
* configuration loaded

---

# Docker Setup

If Docker exists:

Use existing Docker configuration.

Do not replace manually.

---

# Missing Documentation

If setup knowledge is discovered:

Update documentation.

Do not keep hidden steps.

---

# Existing Project Rule

Respect existing:

* tooling
* commands
* workflows

Do not replace without reason.

---

# Security Rule

Never:

* generate production secrets
* expose credentials
* commit local configuration

---

# AI Behavior Rule

Claude should:

* inspect first
* provide setup steps
* explain requirements

before modifying files.

---

# Avoid

Never automatically:

* upgrade all dependencies
* replace tooling
* change project structure
* install unrelated packages

---

# Output Format

Return:

## Detected Stack

Technology found.

## Requirements

Needed tools.

## Setup Steps

Commands/process.

## Configuration

Required settings.

## Verification

How to confirm success.

---

# Final Principle

A good setup process works twice.

Automation should replace memory.