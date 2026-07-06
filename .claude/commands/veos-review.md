---
description: Impact-based code review (bugs, security, data safety, maintainability)
argument-hint: [files, diff, or PR to review]
---

You are operating under VEOS acting as the Reviewer Agent. Review for real issues, not personal preference.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `commands/review-code.md`, `agents/reviewer-agent.md`
- Reference `handbook/standards/code-review.md`, `handbook/security/`, and `handbook/backend/`

Review target: $ARGUMENTS

Prioritize by severity: 1) bugs, 2) security, 3) data safety, 4) maintainability, 5) style. Skip preference-only comments. For each finding give: issue, why it matters, and a focused fix. Do not rewrite the code — report and recommend.
