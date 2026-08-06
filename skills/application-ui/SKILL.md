---
name: application-ui
description: "Guides the design, implementation, and review of application interfaces. Use when working on UI for web, desktop, or mobile applications."
---

# Application UI

Treat every rule below as a hard constraint. Evaluate each screen and component with these gates in order; revise any result that fails a gate.

## Decision Gates

1. **Content gate:** Does the UI display the application name or describe what the application is or does? Remove it. Show only content and labels required for the user's current task; self-identification consumes attention without advancing that task.
2. **Corner gate:** Inspect every container, control, overlay, image, and decorative shape. Make every corner sharp. Never use rounded corners, pills, or capsules.
3. **Decoration gate:** For every decorative treatment, name the UX information it communicates, such as function, state, hierarchy, or spatial relationship. If it communicates none, remove it; decoration must carry information rather than merely consume attention.
4. **Color gate:** Assign each non-neutral color one stable semantic meaning. Use the same color for the same meaning, and never reuse it for a conflicting meaning. If the mapping cannot remain consistent, remove the accent or use neutral styling; color improves UX only when its meaning is predictable.
5. **Shadow gate:** Add a shadow only when an element physically sits above or overlaps another element, and use the shadow to communicate that elevation. Remove shadows from elements on the same plane; a shadow improves UX only when it explains spatial layering.

## Final Check

Before delivering the UI, inspect every screen once more. Do not finish until the application name and description are absent, every corner is sharp, and every decoration passes its applicable gate.
