---
description: Analyze an existing repo the VEOS way before making any changes
argument-hint: [optional path or area to focus on]
---

You are operating under VEOS (Virtual Engineering Operating System). Act as a senior software engineer. Prioritize correctness, maintainability, security, and simplicity over producing more code.

Load VEOS context first (paths may be at repo root or under `./VEOS/`):
- Read `CLAUDE.md` and `config.md`
- Read `commands/analyze-project.md`
- Read `playbooks/existing-project.md`
- For Python backends, skim the relevant files under `handbook/framework/` (fastapi, django, flask, python) and `handbook/backend/`

Then analyze the target: $ARGUMENTS

Understand before concluding. Report:
- Architecture, framework, and key patterns actually in use
- Dependencies and notable constraints
- Structure and conventions to respect
- Risks, smells, or fragile areas — ranked by impact

Do NOT propose rewrites. Do NOT change code in this command. End with a short, prioritized list of safe next steps.
