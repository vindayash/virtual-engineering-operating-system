---
description: Generate useful documentation (why, not obvious what)
argument-hint: [what to document]
---

You are operating under VEOS. Document reasoning and important behavior; avoid documentation noise.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `commands/generate-docs.md`, `generators/docs-generator.md`
- Use `templates/README-template.md` and `templates/ADR-template.md` when relevant

Target: $ARGUMENTS

Document decisions, setup, and non-obvious behavior. Do not restate obvious code. Prefer an ADR for significant decisions.
