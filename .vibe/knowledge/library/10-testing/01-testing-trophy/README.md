---
title: Testing Trophy Strategy
source: Internal + Kent C. Dodds
url: https://kentcdodds.com/blog/the-testing-trophy-and-testing-classifications/
authority: High
version: 1.0
last_verified: 2026-09-23
---

# Testing Trophy Strategy

## Overview
The **Testing Trophy** (coined by [Kent C. Dodds](https://kentcdodds.com/blog/the-testing-trophy-and-testing-classifications/)) prioritizes **integration tests** over unit or E2E tests. This aligns with modern best practices for applications with rich client-side logic (e.g., React + TanStack).

## Distribution
| Layer          | Tool               | Coverage Target | Purpose                          |
|----------------|--------------------|------------------|----------------------------------|
| **Static**     | TypeScript + ESLint | ~10%             | Catch type errors early.         |
| **Unit**       | Vitest             | ~20%             | Pure functions, utilities.       |
| **Component**  | Storybook + Vitest | ~20%             | UI rendering, interactions.      |
| **Integration**| Vitest + MSW       | ~50%             | Cross-boundary logic (API + UI). |
| **E2E**        | Playwright         | ~20%             | Critical user journeys.          |

## Why This Works for Our Stack
- **Vite/React/TanStack**: Heavy client-side logic → **integration tests** catch most bugs.
- **GraphQL/Prisma**: Contract testing (Codegen) + DB constraints → **integration tests** verify real behavior.
- **Multi-tenant**: E2E tests for **tenant isolation** (release-blocking).

## When to Use E2E
- Auth flows (Okta PKCE).
- Cross-page workflows (e.g., "Create Project → Add Task").
- Tenant isolation (e.g., "Tenant A cannot access Tenant B’s data").
- **Not** for trivial UI checks (use Storybook + Vitest instead).

## Anti-Patterns
- **Test Pyramid**: Over-emphasizes unit tests (hard to maintain for complex UIs).
- **E2E Everything**: Slow, flaky, and expensive.
- **No Integration Tests**: Misses bugs at the boundaries (API + UI + state).