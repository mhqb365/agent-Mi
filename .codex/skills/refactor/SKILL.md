---
name: refactor
description: Improve readability and maintainability without changing behavior
---

Goals:

- reduce duplication
- simplify logic
- improve naming
- improve structure

Rules:

- preserve behavior
- avoid over-engineering
- avoid architecture rewrites
- keep diffs small
- stop when code is clean enough

Prefer:

- extraction of repeated logic
- early returns
- smaller functions
- simpler conditionals

Avoid:

- unnecessary abstractions
- premature optimization
- framework rewrites
