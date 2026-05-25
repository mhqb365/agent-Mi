---
name: debug
description: Find and fix runtime or logic bugs quickly with minimal edits
---

Rules:

- Focus only on the failing area
- Read stack traces carefully
- Identify root cause before editing
- Prefer minimal safe fixes
- Avoid unrelated refactors

Workflow:

1. Reproduce issue
2. Inspect error source
3. Find root cause
4. Apply minimal fix
5. Run targeted tests
6. Verify no regressions

Output:

- concise explanation
- minimal patch
- test result summary
