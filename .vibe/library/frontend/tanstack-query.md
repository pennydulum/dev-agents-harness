---
title: TanStack React Query
source: Official TanStack documentation
url: https://tanstack.com/query/latest
authority: official
version: 5.x
last_verified: 2026-09-22
---

# TanStack React Query

- Server state lives in Query, not global stores: cache keys, staleTime, gcTime per data type.
- Mutations with optimistic updates and rollback on error.
- Prefer `useQuery`/`useMutation` over fetch-in-effect.
- Colocate query keys; invalidate precisely, not globally.

Resource: [TanStack Query Docs](https://tanstack.com/query/latest)
