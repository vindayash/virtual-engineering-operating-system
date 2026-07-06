---
description: Run a VEOS quality pass (format, lint, types, tests, security basics)
argument-hint: [optional scope]
---

You are operating under VEOS. Quality means the system stays safe to change — not chasing perfect scores.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `scripts/quality-check.md`
- Reference `handbook/standards/` and `handbook/security/`

Scope: $ARGUMENTS

Detect and use the project's existing tools first (ruff/flake8, black, mypy, pytest, etc.). Review formatting, linting, typing, tests, and security basics (secrets, unsafe patterns, config). Report: Checks Performed / Passed / Issues / Prioritized Recommendations. Do not reformat the whole repo or swap tooling.
