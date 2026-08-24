---
name: context-management
description: Use when tool output may be large — builds, test runs, searches, logs — or when the parent context is filling up. Delegate noisy operations to sub-agents, read only relevant file sections, and return conclusions instead of raw dumps.
---
# Context Management

## Goal

Keep the parent agent's context focused on decisions and actionable information.

## Procedure

1. Estimate expected tool output.
2. If output is likely large, delegate it.
3. Ask the sub-agent to analyze rather than dump output.
4. Read only relevant file sections.
5. Avoid repeating already-known queries.
6. Return concise summaries.

## Rule

Raw evidence is useful only when the parent agent needs the exact evidence to make a decision. Otherwise return conclusions.
