---
title: Next.js App Router
source: Official Next.js documentation
url: https://nextjs.org/docs
authority: official
version: 15.x
last_verified: 2026-09-22
---

# Next.js (App Router)

- **Server Components**: default; add "use client" only for interactivity (state, effects, event handlers).
- **Server Actions** for mutations; **Route Handlers** for API endpoints.
- **Caching**: request memoization, data cache, full route cache; ISR and on-demand revalidation via tags.
- **Streaming/Suspense** for slow segments; avoid blocking the shell on non-critical data.

Rule of thumb: push work to the server; keep the client bundle small.

Resource: [Next.js Docs](https://nextjs.org/docs)
