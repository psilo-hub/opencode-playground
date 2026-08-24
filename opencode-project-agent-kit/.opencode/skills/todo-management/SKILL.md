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

Before starting an item, verify its dependencies are satisfied and identify blocked items.

When an item changes status, update dependent items where necessary.

Prefer implementation phases that unblock meaningful downstream work.
