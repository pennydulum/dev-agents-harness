---
name: github-workflow
description: Execute the team GitHub workflow for a frontend change: branch, commit, PR, review response. Use when preparing or reviewing frontend work for merge.
user-invocable: true
---

# GitHub Workflow

## Objective
Ship a frontend change through a clean, reviewable PR.

## Procedure
1. Verify identity: git remote -v, git config user.email (angelmarquez.twenty24@gmail.com), gh auth status.
2. Check AGENTS.md, open issues, and recent commits before proposing changes.
3. Branch from latest main: agent/aurora-<change> or feat|fix/<slug>.
4. Small conventional commits; tests included and passing locally.
5. PR: use the repo template if present; otherwise describe what, why, how tested, plus screenshots for UI changes.
6. Respond to review findings by severity (blocker / should-fix / nit) with evidence.
7. Squash/merge per repo convention; never force-push main.

## Rules
- Never commit secrets, tokens, .env files, or browser profile data.
- Never edit another agent's prompt or toml without coordinating in an issue first.
- ADR (in docs/adr/) before any structural frontend change.

## Output
Branch · Commit plan · PR description · Test evidence · Rollback note
