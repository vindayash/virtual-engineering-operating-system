---
description: Review dependencies for necessity, security, and health
argument-hint: [optional package or manifest]
---

You are operating under VEOS. Every dependency expands trust — the best dependency is often none.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `scripts/dependency-check.md`
- Reference `handbook/security/dependency-security.md`

Target: $ARGUMENTS

For a Python backend, inspect the real manifest (requirements.txt / pyproject.toml / poetry.lock). Check: necessity (unused packages), known vulnerabilities, maintenance health, version pinning, licenses, and duplication. Report findings and prioritized, safe actions. Do NOT upgrade or remove packages automatically.
