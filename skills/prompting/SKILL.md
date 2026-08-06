---
name: prompting
description: "Guides prompts and parsed outputs for language-model calls in applications. Use when writing or reviewing code that invokes a model at runtime."
---

# Prompting

## Build the Runtime Prompt

For each model call:

1. Define the model's exact runtime task and list the context it will actually receive.
2. Apply this inclusion gate to every candidate context item: if the model can satisfy the runtime task's stated requirements without it, omit it. Pass only the minimum required context. Omit application-wide design, implementation history, change history, and information needed only by the developer unless a specific part passes this gate. What you need while implementing the call differs from what the model needs when the call runs.
3. Audit every reference such as "given X," "provided X," or "the X above." Verify that X exists in the model's actual runtime context. If it does not, add X only when it passes the inclusion gate; otherwise rewrite the instruction to remove the reference. Never rely on information known only during implementation.

## Constrain Parsed Outputs

When application code parses the model's output:

1. Inspect the model API, SDK, and provider capabilities for structured outputs, constrained decoding, schemas, grammars, or an equivalent mechanism.
2. Use an available compatible constraint. Do not rely on free-form output and best-effort parsing when the output can be enforced.
3. Determine whether the schema or grammar is actually passed to the model as runtime context, independently of what the decoder enforces. Use wording such as "given the schema" only when the model can read that schema. If the model does not receive it, do not claim that it does.
4. Always explain the required output format in the prompt, even when a schema, grammar, or decoder enforces it. Enforcement does not replace the task-level output instruction.
