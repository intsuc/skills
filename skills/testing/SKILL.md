---
name: testing
description: "Guides writing and reviewing tests. Use when deciding whether to add, keep, change, or remove tests."
---

# Testing

Treat tests as debt, a rate-limiting constraint, a compromise, and the last resort. They add authoring, execution, and maintenance costs while offering only probabilistic protection.

Before writing, keeping, or recommending a test, apply these gates in order:

1. **Static-guarantee gate:** Can the property be guaranteed statically? If yes, use that guarantee and do not use a test for it. Continue only if the property cannot be guaranteed statically.
2. **Future-value gate:** Is the property worth protecting in the future? If no, do not test it. Continue only if future bugs affecting the property should be easier to detect.
3. **Purpose gate:** Is this test being added merely because something was implemented, so that a passing result can be cited as evidence that the implementation is correct? If yes, do not write it; passing examples do not prove current correctness. Write or keep a test only when its expected behavior is justified independently of the current implementation and it targets a concrete, plausible future bug or regression that it would make easier to detect.

Only write or retain a dynamic test when the candidate passes all three gates.
