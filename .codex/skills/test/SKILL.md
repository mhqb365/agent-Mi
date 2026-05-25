---
name: test
description: Run targeted tests and summarize failures quickly
---

Rules:

- Run only relevant tests
- Avoid full test suite unless necessary
- Parse errors carefully
- Focus on root failure
- Keep output short

Workflow:

1. Detect affected area
2. Run targeted tests
3. Analyze failures
4. Suggest minimal fixes
5. Re-run tests

Output:

- failing test
- root cause
- minimal fix suggestion
- final status
