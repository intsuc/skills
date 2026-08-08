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
3. **Clause-value gate:** State the useful current information directly. Then test every additional clause independently:
   - Remove the clause.
   - Would its absence permit a concrete, plausible wrong action or decision, or require material rediscovery in a future task?
   - If no, delete it. If yes, keep only the minimum wording that prevents that cost.

   Apply this test to prior states and rejected alternatives alike. Prefer `B` to both `A used to be true, but now B` and `not A, but B`. Keep the `A` clause only when it passes the test independently. Every retained clause is another claim to verify and keep synchronized with the code.

## Rewriting Existing Explanations

Do not patch an isolated sentence or clause. Reconsider the entire explanation against the gates above, draft its complete replacement, and replace it as a unit. This prevents ad hoc additions, redundancy, and obsolete information from accumulating. The need for this full rewrite is itself evidence that natural-language explanations are expensive to maintain.
