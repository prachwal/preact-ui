---
name: preact-ui
description: Use when designing, refactoring, or reviewing Preact pages and components, including component structure, state, hooks, forms, routing, fetches, accessibility, SCSS integration, and tests.
---

# Preact UI Skill

Use this skill when building Preact pages or component systems.

## Core approach

1. Start with the page structure and data flow.
2. Keep components small and composable.
3. Push state up only when multiple children need it.
4. Prefer simple hooks and derived values over premature abstraction.
5. Treat accessibility and responsiveness as design constraints, not cleanup tasks.

## Workflow

1. Identify the page role:
   - marketing page
   - dashboard
   - form flow
   - content page
   - interactive tool
2. Define the layout hierarchy before writing component code.
3. Separate presentational and data-fetching concerns when it improves clarity.
4. Model state intentionally:
   - local state for local UI
   - lifted state for shared interactions
   - derived state instead of duplicated state
5. Integrate SCSS through predictable class names and component-scoped partials.
6. Add accessibility checks for keyboard, labels, focus order, and semantics.
7. Add tests for user-visible behavior, not implementation details.

## Recommended structure

- `src/components/`
- `src/features/`
- `src/routes/`
- `src/hooks/`
- `src/services/`
- `src/styles/`

## Component rules

- Keep one main concern per component.
- Prefer props that describe intent, not DOM mechanics.
- Use semantic HTML first.
- Avoid overusing context when props are simpler.
- Keep state close to the interaction it belongs to.

## Hooks and state

- Use hooks for lifecycle, subscriptions, and derived async data.
- Memoize only when profiling or data shape justifies it.
- Prefer explicit loading, error, and empty states.
- Keep effects narrow and deterministic.

## Forms

- Use controlled inputs when validation or live feedback matters.
- Expose clear validation messages.
- Keep submit state, pending state, and error state visible.
- Preserve keyboard flow and focus after submit or error.

## Fetching data

- Centralize API calls in a service layer when reuse matters.
- Handle loading, error, retry, and cancellation paths.
- Keep transport details out of presentational components.

## SCSS integration

- Use a stable class naming scheme.
- Pair components with focused SCSS partials.
- Reuse tokens, mixins, and spacing scales from the SCSS system.
- Keep responsive behavior and theme variants aligned with the design system.

## Accessibility

- Use semantic landmarks, headings, labels, and buttons.
- Ensure focus states are visible.
- Support keyboard-only interaction.
- Keep color contrast readable in all themes.

## Testing

- Test visible behavior.
- Cover interactive states, validation, and async loading/error paths.
- Prefer realistic component tests over brittle implementation snapshots.

## References

- [references/layout.md](references/layout.md): page structure and composition
- [references/state.md](references/state.md): state, hooks, and data flow
- [references/forms.md](references/forms.md): form patterns and validation
- [references/accessibility.md](references/accessibility.md): accessible UI rules
