---
description: Initialize a new project in an empty repository via the interview and bootstrap workflow.
agent: orchestrator
---

Run the project initialization workflow:

1. Inspect the repository state first. If meaningful code or a completed PROJECT.md already exists, summarize what you found and confirm before proceeding.
2. Delegate to the interviewer for the adaptive discovery interview — one question at a time, concise options, progress persisted in `.opencode/state/project-interview.md`.
3. Once information is sufficient, have the bootstrap completed per the `project-bootstrap` skill: blueprint, `PROJECT.md`, module structure, module `README.md`/`TODO.md` files, `DECISIONS.md` where needed, and the initial dependency-aware roadmap.
4. Return a concise summary: created files, module list, initial TODO phases, open questions.

Do not invent major requirements the user did not provide. Do not start implementation planning before the roadmap exists.

Session input:

$ARGUMENTS
