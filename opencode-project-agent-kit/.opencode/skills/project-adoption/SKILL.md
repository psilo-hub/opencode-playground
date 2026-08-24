---
name: project-adoption
description: Use ONLY when adopting this kit into an existing repository. Analyzes the codebase, classifies gaps as AUTO/ASK/SUGGEST, applies additive changes, and negotiates conflicts with existing configuration one question at a time.
---
# Project Adoption

1. Inspect before asking. Infer everything safely inferable.
2. Classify every gap:
   - AUTO — additive files: PROJECT.md, module README.md/TODO.md, generated build skill, DECISIONS.md where evident.
   - ASK — merges and conflicts: existing AGENTS.md, existing opencode.json keys, collisions inside `.opencode/`, legacy TODO lists. Ask exactly one question at a time with concise options.
   - SUGGEST — structural advice such as module splits or renames. Report only, never execute.
3. Generate the build skill at `.opencode/skills/<buildtool>/SKILL.md` from `project-bootstrap/templates/build-skill-SKILL.md`. JVM/Maven projects use the bundled `maven` skill unchanged.
4. Reuse the `project-bootstrap/templates/` files for every generated document so adopted projects are indistinguishable from bootstrapped ones.
5. Mark every generated statement that restates code facts as inferred until confirmed by a human or by unambiguous code evidence.
6. Persist progress in `.opencode/state/project-adoption.md` so an interrupted adoption resumes.

Never overwrite or silently modify existing files.
