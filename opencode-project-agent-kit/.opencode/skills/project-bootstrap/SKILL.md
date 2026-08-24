---
name: project-bootstrap
description: Use ONLY when initializing a new project from an empty repository after the interview is complete. Creates PROJECT.md, the initial module structure, module README and TODO files, DECISIONS records, and the initial dependency-aware roadmap.
---
# Project Bootstrap

For an empty project:

1. Complete the project interview.
2. Persist the project blueprint.
3. Create `PROJECT.md`.
4. Create the initial directory/module structure.
5. Create module `README.md` and `TODO.md`.
6. Create `DECISIONS.md` where needed.
7. If the interviewed build system is not JVM/Maven, create a build-verification skill for it at `.opencode/skills/<buildtool>/SKILL.md` from `templates/build-skill-SKILL.md`, filled with the real build and test commands captured during the interview. JVM/Maven projects use the bundled `maven` skill unchanged.
8. Generate initial TODO IDs and dependency relationships.
9. Create the initial implementation roadmap.

Do not invent requirements not established during the interview.
