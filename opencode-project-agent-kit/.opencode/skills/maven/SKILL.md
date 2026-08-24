---
name: maven
description: Use when running Maven builds or tests in JVM projects. Choose the narrowest useful goal, route noisy output through the tester sub-agent, and analyze failures down to the first root cause without pasting complete logs.
---
# Maven Verification

Prefer the narrowest useful Maven command.

Examples:
- specific test,
- module test,
- affected module,
- full verification.

If substantial output is expected, execute through the tester sub-agent and return a concise analysis.

When analyzing failures, identify:
- failing module,
- failing test/goal,
- compilation errors,
- first meaningful root cause,
- likely fix,
- whether failures appear related or independent.

Do not paste complete Maven logs into the parent context.
