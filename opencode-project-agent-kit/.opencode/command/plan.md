---
description: Produce a dependency-aware implementation plan for the given goal without changing anything.
agent: orchestrator
---

Produce an implementation plan for the following goal. Planning only — no edits, no implementation:

Goal: $ARGUMENTS

1. Identify affected modules and read their `README.md` and `TODO.md`.
2. Delegate planning to the planner (read-only). The plan must include: affected modules, prerequisite TODO IDs, ordered implementation steps, test strategy, architectural risks, and required documentation changes.
3. Verify the plan respects TODO dependencies per the `todo-management` skill.
4. Return the concise plan and flag blocked prerequisites or open questions.

Do not implement anything as part of this command.
