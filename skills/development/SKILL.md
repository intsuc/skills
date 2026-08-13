---
name: development
description: "Guides agent-led software development organized by session turns. Use when making changes to software."
---

# Development

Discard conventional human software-development thinking. Treat development as a continuous sequence of turns within the current session.

Never divide development into `v0`, `0.1`, `1.0`, `MVP`, or any other version boundary. Use the turn, not the version, as the unit of development.

## Multi-Turn Changes

Before starting a software change that is expected to require more than one turn, use the goal feature to create one objective with a verifiable stopping condition. Preserve the per-turn invariant throughout the goal.

## Per-Turn Invariant

Use every turn to make complete changes to the software.

End every turn with usable software. Never leave any software change partially implemented.

## Complexity Defaults

Before adding compatibility behavior or a fallback, identify an explicit requirement in the current task, governing project instructions or specification, or a mandatory external contract.

- If a requirement exists, implement only its stated scope. Make each fallback's trigger and alternative behavior explicit and test them.
- Otherwise, implement exactly the current contract:
  - Do not add backward compatibility for superseded APIs, inputs, configuration, data formats, or behavior.
  - Do not add forward compatibility for hypothetical future versions, fields, enum values, capabilities, or environments.
  - Do not add implicit fallbacks. When the intended path cannot proceed, return a clear, actionable error instead of silently choosing another path, using stale or guessed data, or substituting an empty or null result.

When a requested change replaces a contract, migrate all in-scope callers, tests, documentation, and persisted data in the same turn, then remove the old aliases, adapters, version branches, dual reads, and dual writes. Use an explicit one-time data migration when necessary; do not continue supporting the old format at runtime.

Treat a default value declared by the current contract as normal behavior, not a fallback. Treat explicitly supported targets and capabilities as the current contract, not forward compatibility. Do not infer a compatibility requirement solely from legacy code.

These defaults prevent speculative branches and hidden behavior from accumulating in the codebase.
