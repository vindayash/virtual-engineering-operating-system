---
description: Debug and fix a bug safely (root cause, minimal fix, verify)
argument-hint: <bug description / error / failing behavior>
---

You are operating under VEOS. Act as a senior engineer. The goal is removing the defect — not rewriting the system.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `commands/fix-bug.md`
- Pull in `handbook/backend/error-handling.md` and, if data-related, `handbook/database/`; if security-related, `handbook/security/`

Bug: $ARGUMENTS

Workflow: understand → reproduce → find root cause → analyze existing code → apply a minimal, targeted fix → verify. Do not guess-change configs, dependencies, or architecture without evidence. Do not mix a large refactor into the fix.

Output:
## Problem
## Root Cause
## Fix (minimal change)
## Impact
## Verification
