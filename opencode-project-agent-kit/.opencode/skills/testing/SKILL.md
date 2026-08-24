---
name: testing
description: Use when deciding how to verify changes. Pick the smallest test scope that gives real confidence — focused regression, module, integration, then broader suites — and analyze failures instead of merely reporting exit codes.
---
# Testing

Choose the smallest test scope that provides meaningful confidence.

Prioritize:
1. focused regression tests,
2. affected module tests,
3. relevant integration tests,
4. broader project verification.

Analyze failures rather than merely reporting command failure.

Before declaring work complete:
1. verify the requested behavior,
2. run appropriate tests,
3. inspect the final diff,
4. check architectural consistency,
5. check documentation and TODO state,
6. ensure unrelated changes were not introduced.
