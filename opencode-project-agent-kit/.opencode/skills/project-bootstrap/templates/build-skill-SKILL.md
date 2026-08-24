---
name: <buildtool>
description: Use when running builds or tests for this project's <buildtool> setup. Choose the narrowest useful command, route noisy output through the tester sub-agent, and analyze failures down to the first root cause without pasting complete logs.
---
# <Build Tool> Verification

Prefer the narrowest useful command.

Project commands captured during the interview:

- build: `<command>`
- module/component tests: `<command>`
- full verification: `<command>`

If substantial output is expected, execute through the tester sub-agent and return a concise analysis.

When analyzing failures, identify:

- failing module,
- failing test/goal,
- compilation errors,
- first meaningful root cause,
- likely fix,
- whether failures appear related or independent.

Do not paste complete logs into the parent context.
