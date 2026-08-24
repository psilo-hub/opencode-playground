# AGENTS.md — Project Operating System

## Purpose

You are working in a potentially large, continuously evolving codebase. Optimize simultaneously for:

1. Correctness.
2. Maintainability.
3. Architectural integrity.
4. Domain clarity.
5. Testability.
6. Efficient use of the context window.

Treat the repository as a long-lived software system, not a collection of isolated files.

## Operating hierarchy

The system has three layers:

- **AGENTS.md** — global rules and invariants (this file).
- **Agents** — roles and permissions defined in `.opencode/agents/<name>.md`.
- **Skills** — reusable procedures defined in `.opencode/skills/<name>/SKILL.md`.

Agents must follow this file and load the skills applicable to their current activity. Procedures live in skills; this file states only invariants and points to them.

### Agent roster

| Agent | Responsibility |
|-------|----------------|
| `orchestrator` | Owns the workflow; delegates investigation, planning, implementation, verification. |
| `interviewer` | One-question-at-a-time project discovery; creates the blueprint. |
| `planner` | Read-only dependency-aware implementation plans. |
| `architect` | Read-only module boundaries, DDD structure, architectural decisions. |
| `explorer` | Read-only context-minimizing code location. |
| `investigator` | Read-only deep analysis and root-cause work. |
| `implementer` | Writes production code and tests following TDD, Clean Code, DDD. |
| `tester` | Runs builds/tests; returns concise actionable verdicts. |
| `reviewer` | Read-only independent change review, findings ordered by severity. |

Behavioral details live in each agent definition, never here.

## Context management invariants

The main agent's context is a scarce resource.

- Search before reading; inspect only the most relevant results. Procedure: `repository-exploration`.
- Delegate operations likely to produce large output — builds, test suites, static analysis, large repository searches, log analysis, dependency trees, git history investigations — and consume conclusions, not raw logs. Procedure: `context-management`.
- Sub-agent reports must summarize: status, relevant findings, failures/errors, likely cause, recommended next action.

## Skills index

Load the matching skill before performing these activities:

| Activity | Skill |
|----------|-------|
| Writing or reviewing production code | `clean-code` |
| Implementing behavior changes or tests | `tdd` |
| Modeling domain concepts | `ddd` |
| Adding abstractions or dependencies; boundary checks | `architecture` |
| Recording durable decisions | `architecture-decisions` |
| Verifying changes | `testing`; build tooling: bundled `maven` (JVM) or the project-generated `<buildtool>` skill created during bootstrap |
| Creating or updating roadmaps | `todo-management`, `task-decomposition` |
| Locating code or structure | `repository-exploration` |
| Handling large outputs under context pressure | `context-management` |
| Discovering a new project | `project-interview`, then `project-bootstrap` |

## Modules and documentation

Every project module must contain:

- `README.md`
- `TODO.md`

and preferably also `DECISIONS.md`.

Section content follows the templates in `.opencode/skills/project-bootstrap/templates/`. TODO item format, `<MODULE>-<NUMBER>` identifiers, and cross-module dependency references follow the `todo-management` skill.

## Existing repositories

Inspect before asking questions; infer what can safely be inferred; ask only about important missing information. Details: `project-interview`.

## Project bootstrap

In an empty directory: run the project interview, then bootstrap per the `project-bootstrap` skill (blueprint → `PROJECT.md` → structure → module docs → roadmap) before implementation planning.

Do not invent major project requirements that the user has not provided.

## Verification

Prefer the narrowest verification that gives useful confidence, and complete the pre-completion checklist — see the `testing` skill.

## General rule

When several approaches are technically viable, prefer the one that:

1. uses less unnecessary context,
2. introduces less complexity,
3. preserves domain clarity,
4. is easier to test,
5. is consistent with project architecture,
6. will remain understandable as the codebase grows.
