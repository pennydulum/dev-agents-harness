---
title: Frontend Testing: Vitest, RTL, MSW, Playwright
source: Official project documentation
url: https://vitest.dev/guide/
authority: official
version: Vitest 1.x / RTL 14.x / MSW 2.x / Playwright 1.x
last_verified: 2026-09-22
---

# Frontend Testing Stack

- **Vitest**: unit tests for utilities and hooks.
- **React Testing Library**: test behavior and roles, not implementation; query by role/label.
- **MSW**: intercept network at the service-worker level; one handler per endpoint shape.
- **Playwright**: E2E for critical user flows only; keep them few and stable.

Strategy: maximize confidence per test; use real boundaries where practical.

Resource: [Vitest](https://vitest.dev/guide/) · [RTL](https://testing-library.com/docs/react-testing-library/intro/) · [MSW](https://mswjs.io) · [Playwright](https://playwright.dev/docs/intro)
