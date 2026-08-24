---
description: Adopt this kit into an existing project - analyze the repository, report gaps against the expected structure, apply obvious additions, and ask before touching existing files.
agent: orchestrator
---

Adopt this project into the agent-kit operating model.

Mode: $ARGUMENTS (empty = full adoption; "--dry-run" = analyze and report only).

1. Preflight: verify AGENTS.md, PROJECT.md, .opencode/agents/, .opencode/skills/, and .opencode/command/ exist. If pieces are missing, report exactly which kit files must be copied first and stop. If git reports uncommitted changes, confirm before continuing.
2. Analyze the repository read-only (delegate): languages/ecosystem, build and test commands, CI setup, existing AI-config files (AGENTS.md, CLAUDE.md, .cursorrules, etc.), existing .opencode/ content, and candidate modules with boundaries.
3. Produce a gap report against the expected structure. Tag each item AUTO (additive, safe), ASK (touches existing content), or SUGGEST (advice only). In --dry-run mode, stop after reporting.
4. Apply AUTO items: PROJECT.md draft from analysis; build skill at .opencode/skills/<buildtool>/SKILL.md from the bootstrap template filled with detected commands - skip when the project is JVM/Maven because the bundled maven skill already covers it; module README.md and TODO.md skeletons from the templates, facts marked as inferred; DECISIONS.md entries only where the code makes the decision clear.
5. Resolve ASK items one question at a time: merge strategy for an existing AGENTS.md, missing keys in an existing opencode.json, reconciling legacy TODO lists with todo-management format, collisions inside .opencode/. Persist decisions to .opencode/state/project-adoption.md so an interrupted adoption resumes.
6. Summarize: created or modified files, open questions, recommended next steps such as running /plan for the first roadmap item.

Never overwrite or silently modify existing files. Never invent requirements the code does not show.
