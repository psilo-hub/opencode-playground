---
description: Independently review current changes for correctness, architecture, tests, Clean Code, and DDD quality.
agent: orchestrator
---

Run an independent review of the requested changes.

Scope: $ARGUMENTS (if empty, review the uncommitted working diff).

1. Determine the change set — diff/stat first, no full-file dumps in context.
2. Delegate to the reviewer (read-only). It checks correctness, requirements coverage, tests and regression risk, Clean Code, DDD, module boundaries, dependency direction, duplication, naming, domain language, and documentation/TODO consistency.
3. Report findings ordered by severity, each tagged with its type (BUG / DESIGN / TEST-GAP / DOCS), with file references and a concrete suggestion.
4. End with an overall verdict: approve, approve-with-comments, or request-changes.

The review must not modify any files.
