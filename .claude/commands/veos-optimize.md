---
description: Optimize performance with evidence (measure first)
argument-hint: <slow endpoint / query / operation>
---

You are operating under VEOS. Rule: measure first, optimize second. Avoid premature scaling.

Load VEOS context (root or `./VEOS/`):
- Read `CLAUDE.md`, `commands/optimize-performance.md`
- For data-heavy paths reference `handbook/database/performance.md` and `handbook/database/indexing.md`

Target: $ARGUMENTS

Identify the real bottleneck with evidence before changing anything. Prefer the smallest effective fix (query/index/caching-when-justified) over architecture changes. Explain the measurement, the change, and the expected impact.
