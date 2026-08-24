# opencode-playground

A reusable **project agent kit** for [opencode](https://opencode.ai): one
coordinating agent, eight specialists, fourteen engineering skills, slash
commands for the main workflows, and an enforced permission model — ready
to drop into any repository.

Everything lives in [`opencode-project-agent-kit/`](opencode-project-agent-kit/).

## What's inside

| Piece | Purpose |
|-------|---------|
| `AGENTS.md` | Global operating rules: invariants, agent roster, skills index. |
| `PROJECT.md` | Project blueprint, filled by the interview. |
| `opencode.json` | Minimal config; `default_agent: orchestrator`. |
| `.opencode/agents/` | 9 agent definitions (roles + permission guards). |
| `.opencode/skills/` | 14 skills (`SKILL.md` each) + bootstrap templates. |
| `.opencode/command/` | `/bootstrap`, `/interview`, `/plan`, `/review`. |
| `.opencode/state/` | Resumable interview state (per project). |

## Agent roster

| Agent | Responsibility |
|-------|----------------|
| `orchestrator` | Coordinates and delegates; direct edits need approval. |
| `interviewer` | One-question-at-a-time discovery; persists resumable state. |
| `planner` | Read-only dependency-aware implementation plans. |
| `architect` | Read-only boundaries, DDD structure, decisions. |
| `explorer` | Read-only code location, minimal context output. |
| `investigator` | Deep analysis with a scoped read-only shell allowlist. |
| `implementer` | Writes production code and tests (TDD/Clean Code/DDD). |
| `tester` | Runs builds/tests; reports exact commands + exit codes. |
| `reviewer` | Independent review: severity × type findings. |

Read-only agents cannot edit files or run mutating shell commands;
the full permission matrix lives in each agent definition.

## How work flows

1. Orchestrator receives the task and identifies affected modules.
2. `explorer` locates code; `investigator` diagnoses; `architect` decides boundaries.
3. `planner` produces a dependency-aware plan (TODO IDs, phases, tests).
4. `implementer` implements with TDD; `tester` verifies and reports.
5. `reviewer` independently reviews before work is called done.

For an empty repository, start with the interview instead: it produces the
blueprint, module structure, and initial roadmap before any implementation.

## Quick start — adopt into a project

1. Copy the kit into your project root:

   ```
   AGENTS.md
   PROJECT.md
   opencode.json
   .opencode/          (agents/, skills/, command/)
   ```

   from `opencode-project-agent-kit/` into `<your-project>/`.

2. Restart opencode — config-time files load once at startup.
3. Empty project: run `/bootstrap` and answer the interview.
   Existing project: just describe a task — the orchestrator inspects
   first and asks only what it cannot infer.

You end up with `PROJECT.md`, module skeletons with `README.md`/`TODO.md`,
a phased roadmap, and — for non-JVM projects — a generated build skill
holding your real build/test commands. JVM/Maven projects use the bundled
`maven` skill out of the box.

## Using the kit without copying it

Reference it from your project's `opencode.json` instead:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": ["path/to/opencode-project-agent-kit/AGENTS.md"],
  "skills": { "paths": ["path/to/opencode-project-agent-kit/.opencode/skills"] }
}
```

Slash commands and agents are discovered from `.opencode/` inside the
worktree, so copying remains the recommended setup for full functionality.

## Conventions worth knowing

- TODO items form a dependency graph with `<MODULE>-<NUMBER>` IDs and a
  fixed status vocabulary: `pending`, `in-progress`, `blocked`, `done`.
- Reviews report findings as `<SEVERITY> / <TYPE>` (bug, design,
  test-gap, docs).
- Tester failure reports always name exact commands and exit codes.
