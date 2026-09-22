---
name: architecture-review
description: Analyze an existing software system and produce a structured architecture review. Use for architecture assessments, system reviews, or current-state analysis.
user-invocable: true
---

# Architecture Review

## Objective
Understand the current system before recommending changes.

## Procedure
1. Inspect repo structure, package config, entry points, and existing docs/ADRs.
2. Identify the architecture style and major modules or services.
3. Identify domain boundaries and the ubiquitous language in use.
4. Map dependencies and data ownership.
5. Inspect authentication, authorization, secrets handling, and trust boundaries.
6. Inspect deployment, CI/CD, and environment configuration.
7. Inspect observability: logs, metrics, traces, health checks.
8. Identify risks: coupling, hidden dependencies, single points of failure, missing contracts, scalability limits, operational complexity.
9. Recommend changes with a migration plan and validation plan.

## Rules
- Label every finding fact, assumption, or unknown.
- Cite evidence (file paths, commands run).
- Do not modify code.

## Output
Executive summary · Current architecture · Strengths · Risks · Security · Performance · Reliability · Maintainability · Recommended changes · Migration plan · Validation plan · Open questions
