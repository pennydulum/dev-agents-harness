---
name: github-actions-audit
description: Audit GitHub Actions workflows for supply-chain and permission risk. Use when adding or reviewing workflow files.
user-invocable: true
---

# GitHub Actions Audit

## Objective
Find and fix workflow supply-chain risks before merge.

## Procedure
1. Check every workflow declares an explicit `permissions:` block; default to `contents: read`.
2. Pin every third-party action to a full 40-char commit SHA (not a tag).
3. Scan run steps for unescaped `${{ github.event.* }}` interpolation (script injection).
4. Verify secrets are never echoed and untrusted input never reaches shell or script steps.
5. Check runner choice, environment protection rules, and whether deploys are gated.
6. Produce an actionable remediation list.

## Rules
- Report the exact file:line for each finding.
- Label findings blocker / should-fix / nit with evidence.

## Output
Findings table (workflow, line, issue, severity, fix) · Remediated YAML snippets where useful.
