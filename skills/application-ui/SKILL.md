---
name: application-ui
description: "Guides the design, implementation, and review of application interfaces. Use when working on UI for web, desktop, or mobile applications."
---

# Application UI

Treat every rule below as a hard constraint. Evaluate each screen and component with these gates in order; revise any result that fails a gate.

## Decision Gates

1. **Content gate:** Does the UI display the application name or describe what the application is or does? Remove it. Show only content and labels required for the user's current task; self-identification consumes attention without advancing that task.
2. **Element-source gate:** When the project uses an existing UI system, inspect every custom UI element before creating or retaining it. If a provided element or supported composition satisfies the same role and interaction requirements, use it. Create a custom element only for requirements the system cannot satisfy, and reuse provided elements for every part they can supply. Reusing established elements preserves consistent behavior and interaction patterns across the application.
3. **Styling-source gate:** When the project uses an existing UI system, inspect every custom style before adding or retaining it. If the system provides a styling option that satisfies the same requirement, use it. A mechanism for authoring styles does not make those styles provided by the system. Otherwise, limit the custom style to the unmet requirement and follow the system's existing values and conventions. Keeping one primary styling system preserves consistency across the application.
4. **Corner gate:** Inspect every container, control, overlay, image, and decorative shape. Make every corner sharp. Never use rounded corners, pills, or capsules. Sharp geometry keeps boundaries and alignment explicit instead of adding decorative softness that communicates no task information.
5. **Decoration gate:** For every decorative treatment, name the UX information it communicates, such as function, state, hierarchy, or spatial relationship. If it communicates none, remove it; decoration must carry information rather than merely consume attention.
6. **Color gate:** Assign each non-neutral color one stable semantic meaning. Use the same color for the same meaning, and never reuse it for a conflicting meaning. If the mapping cannot remain consistent, remove the accent or use neutral styling; color improves UX only when its meaning is predictable.
7. **Shadow gate:** Add a shadow only when an element physically sits above or overlaps another element, and use the shadow to communicate that elevation. Remove shadows from elements on the same plane; a shadow improves UX only when it explains spatial layering.

## Final Check

Before delivering the UI, inspect every screen and component against all applicable gates in order. Do not finish until every applicable gate passes. When an existing UI system is present, verify that every remaining custom element or style is limited to a requirement the system cannot satisfy.
