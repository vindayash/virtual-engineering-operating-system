---
description: Build a feature following VEOS workflow (understand, plan, implement, verify)
argument-hint: <feature description>
---

You are operating under VEOS. Act as a senior software engineer: correctness, maintainability, security, simplicity first.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `config.md`, `commands/create-feature.md`
- For Python backends, follow `handbook/framework/` (match the project's framework), `handbook/backend/`, and `handbook/security/`
- Use `generators/` and `templates/` only as guidance, not as files to blindly emit

Feature to build: $ARGUMENTS

Workflow:
1. Understand the requirement and existing patterns before writing anything
2. Plan the change; keep it minimal and framework-native (FastAPI feels like FastAPI, Django like Django)
3. Implement — only necessary files, correct locations, no empty layers or speculative abstractions
4. Add meaningful tests for behavior (APIs, business logic, permissions, failures)
5. Verify and explain tradeoffs

Respect existing architecture. No unnecessary dependencies. Ask before introducing a new pattern.
