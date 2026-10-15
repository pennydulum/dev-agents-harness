---
name: frontend-review
description: Review frontend code for component boundaries, state ownership, accessibility, localization, testing, and performance. Use for PR review or component audit.
user-invocable: true
---

# Frontend Review

## Objective
Review frontend code changes or components before merge.

## Procedure
1. Diff scope: which components, hooks, and state are affected.
2. State ownership: is state in the right place (URL, component, context, React Query, server, session)? Flag any unnecessary global state.
3. Rendering: correct server vs client component split; no accidental client boundary; caching/revalidation intentional.
4. Data: TanStack Query keys, stale times, error/loading/empty/optimistic states covered.
5. Accessibility: semantic HTML, keyboard paths, focus management, ARIA, contrast.
6. Localization: strings externalized; layout survives RTL/longer strings.
7. Tests: Vitest/RTL/MSW/Playwright coverage matches the risk.
8. Performance: bundle impact, unnecessary re-renders, image/asset handling.
9. Style: follows STYLE_GUIDE.md and shadcn/ui conventions.

## Rules
- Label findings blocker / should-fix / nit with evidence (file:line).
- Do not modify code.

## Output
Summary · Findings by severity · State/rendering notes · A11y & i18n notes · Test gaps · Verdict
