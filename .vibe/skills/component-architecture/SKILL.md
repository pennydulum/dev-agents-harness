---
name: component-architecture
description: Design component composition, state ownership, and data flow for a frontend feature before implementation. Use when starting a non-trivial UI feature.
user-invocable: true
---

# Component Architecture

## Objective
Define boundaries before writing components.

## Procedure
1. Restate requirements as observable behaviors (BDD where useful).
2. List screens/components and their responsibility (one concern each).
3. Assign state ownership: URL, component, context, React Query, server, session — no global store by default.
4. Define data flow: server components vs client, query keys, mutations, optimistic updates, revalidation.
5. Design UX states: loading, error, empty, offline.
6. Plan composition with shadcn/ui primitives per STYLE_GUIDE.md.
7. Plan tests at the level the risk justifies.

## Rules
- Prefer the simplest model that meets the requirements.
- Structural or cross-cutting decisions escalate to Orion via an ADR proposal.

## Output
Behaviors · Component map · State ownership table · Data flow (Mermaid) · UX states · Test plan · Open questions
