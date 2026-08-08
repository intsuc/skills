---
name: documentation
description: "Guides decisions about natural-language explanations. Use when writing or editing documentation, doc comments, or code comments."
---

# Documentation

Treat code as the single source of truth. By default, do not add natural-language explanations, including documentation, doc comments, and code comments.

Keep this default strict because explanations are easy to add and therefore proliferate, create duplicate ownership with the code, resist verification, and mislead decisions when wrong or stale.

## Decision Process

Before writing an explanation, apply these gates in order:

1. **Code gate:** Can ordinary code reading reveal the information without a large investigation? If yes, do not write it. Continue only when the information cannot be learned from the code or rediscovering it would require a large investigation every time.
2. **Future-value gate:** Will recording the information materially improve your execution of future tasks? If no, do not write it. Continue only when the information will save useful future work.
3. **Minimum-current-information gate:** Write only the smallest explanation that captures the useful current information. Do not preserve history merely because it once mattered; past information often has no future value. When changing `A` to `B`, write `B`, not `A used to be true, but now B`, unless knowing `A` will help perform a future task.

## Rewriting Existing Explanations

Do not patch an isolated sentence or clause. Reconsider the entire explanation against the gates above, draft its complete replacement, and replace it as a unit. This prevents ad hoc additions, redundancy, and obsolete information from accumulating. The need for this full rewrite is itself evidence that natural-language explanations are expensive to maintain.
