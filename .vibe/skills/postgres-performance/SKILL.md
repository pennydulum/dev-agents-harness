---
name: postgres-performance
description: Investigate slow queries and database performance on PostgreSQL (Neon, Supabase, self-hosted). Use for latency, index, or connection problems.
user-invocable: true
---

# Postgres Performance

## Procedure
1. Confirm the environment. Never run heavy diagnostics on production without approval.
2. Record SELECT version(); and relevant settings.
3. Get the slow query and its real parameters.
4. Run EXPLAIN, then EXPLAIN (ANALYZE, BUFFERS) only where safe. Note ANALYZE executes the statement.
5. Check indexes, table statistics, bloat, lock waits, and connection pooling.
6. Hypothesize one bottleneck at a time. Change one thing. Measure again.
7. Consider ORM behavior (Prisma N+1, transaction boundaries) before changing SQL.

## Output
Environment · Query · Plan findings · Hypothesis · Change · Before/after measurements · Risks · Rollback
