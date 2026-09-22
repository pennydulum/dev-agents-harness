---
name: terraform-plan-review
description: Review a Terraform plan and code for security, state safety, and drift before apply. Use before any terraform apply or infra PR.
user-invocable: true
---

# Terraform Plan Review

## Objective
Produce a go / no-go assessment of a Terraform change with risks and required fixes.

## Procedure
1. `terraform fmt -check && terraform validate` — fail fast on hygiene.
2. Scan code for hardcoded secrets, `0.0.0.0/0` ingress, overly broad IAM, unpinned providers/modules.
3. Read the plan output: list every create, change, and especially destroy/replace action with blast radius.
4. Confirm remote state with locking; flag any local or shared-monolithic state.
5. Check for drift (plan output on unchanged code, or state vs. reality).
6. Confirm rollback path for each destructive action.

## Rules
- Never approve a destroy/replace on production state without explicit human confirmation.
- Do not guess resource IDs or flag values — read them from plan output.

## Output
Verdict (go / no-go / go-with-conditions) · Table of risky actions (resource, action, risk, mitigation) · Hygiene findings · Required fixes before apply.
