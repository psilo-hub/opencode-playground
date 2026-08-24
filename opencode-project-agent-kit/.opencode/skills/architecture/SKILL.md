---
name: architecture
description: Use when adding dependencies, abstractions, modules, or services, or when checking module boundaries and dependency direction. Guides ownership checks, existing-abstraction search, README and DECISIONS review, and cross-module impact assessment before introducing new structure.
---
# Architecture

Before introducing a dependency or abstraction:

1. Identify the owning module.
2. Check dependency direction.
3. Check `README.md` and `DECISIONS.md`.
4. Search for existing abstractions.
5. Assess cross-module impact.

Prefer explicit boundaries and stable interfaces.

Document significant architectural decisions.
