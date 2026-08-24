# Project

This repository is managed according to the project operating rules in `AGENTS.md`.

If this is a newly initialized project, start with the project interview before making significant implementation decisions.

## Documentation structure

Each module should contain:

- `README.md` — purpose, architecture, domain concepts, constraints.
- `TODO.md` — phased implementation roadmap and cross-module dependencies.
- `DECISIONS.md` — important architectural/domain decisions, when applicable.

See `PROJECT.md` for the high-level project definition.

## Slash commands

Workflow entry points defined in `.opencode/command/`:

| Command | Purpose |
|---------|---------|
| `/bootstrap` | Initialize a new project in an empty repository (interview → blueprint → roadmap). |
| `/interview` | Start or resume the one-question-at-a-time discovery interview. |
| `/plan <goal>` | Produce a read-only, dependency-aware implementation plan. |
| `/review [scope]` | Independently review changes; findings ordered by severity. |

Commands require an opencode restart after being added or changed.

