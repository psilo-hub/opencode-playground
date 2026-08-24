---
name: todo-management
description: Use when creating or updating TODO.md roadmaps. Treats items as a dependency graph with globally unique <MODULE>-<NUMBER> IDs, explicit cross-module references, and status updates that propagate to dependents.
---
# TODO Management

TODO items form a dependency graph.

Use globally unique IDs:

`<MODULE>-<NUMBER>`

Each item should include:

- title,
- status,
- purpose,
- dependencies,
- affected module(s),
- useful implementation notes.

Cross-module dependencies must reference concrete TODO IDs.

## Status values

Every item carries exactly one status:

- `pending` — not started; dependencies may be unmet.
- `in-progress` — actively being implemented.
- `blocked` — cannot proceed; the entry must name the blocking TODO ID or decision.
- `done` — verified complete (tests/build evidence).

No other status values are allowed. Moving an item to `done` requires verification, not just finished code.

Before starting an item, verify its dependencies are satisfied and identify blocked items.

When an item changes status, update dependent items where necessary.

Prefer implementation phases that unblock meaningful downstream work.
