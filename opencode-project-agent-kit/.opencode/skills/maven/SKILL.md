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
