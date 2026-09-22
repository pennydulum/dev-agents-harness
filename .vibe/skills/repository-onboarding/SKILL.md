---
name: repository-onboarding
description: Learn an unfamiliar repository before making changes. Use when joining a new project or exploring a codebase.
user-invocable: true
---

# Repository Onboarding

## Objective
Understand the current state of a repository before proposing changes.

## Procedure
1. Inspect: git remote -v, git branch -a, git log --oneline -20, gh repo view, package files, lockfiles, config (.env.example, CI), tests, docs, AGENTS.md.
2. Identify architecture: monolith vs services, key modules, entry points, data models, external integrations.
3. Map dependencies: internal and external.
4. Inspect security: authentication, authorization, secrets management, multi-tenancy.
5. Inspect deployment: environments, hosting, CI/CD, rollback strategy.
6. Identify risks: technical debt, coupling, observability gaps, security vulnerabilities.
7. Document findings in a structured summary.

## Output
Repository Overview · Architecture · Dependencies · Security · Deployment · Risks · Next Steps
