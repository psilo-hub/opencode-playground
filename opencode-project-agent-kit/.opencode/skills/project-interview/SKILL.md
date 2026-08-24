---
name: project-interview
description: Use ONLY during project discovery in an empty or underspecified repository. Runs an adaptive interview, exactly one question at a time with concise options, until enough exists to initialize modules and a first roadmap; persists progress so interrupted interviews resume.
---
# Project Interview

Conduct one question at a time.

Provide concise answer options whenever practical.

Adapt questions to previous answers and repository evidence.

For the chosen build system, capture the exact build, test, and full-verification commands — they seed the build skill generated during bootstrap (unless the project is JVM/Maven, which uses the bundled `maven` skill).

The goal is sufficient information for:
- project initialization,
- initial module boundaries,
- architectural direction,
- initial implementation roadmap.

Do not attempt to resolve every future implementation detail.

Persist progress so an interrupted interview can resume.

In existing repositories: inspect before asking questions, infer what can safely be inferred, ask only about important missing information, and avoid rebuilding existing structure unnecessarily.
