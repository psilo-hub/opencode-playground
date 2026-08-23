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

When an item changes status, update dependent items where necessary.

Prefer implementation phases that unblock meaningful downstream work.
