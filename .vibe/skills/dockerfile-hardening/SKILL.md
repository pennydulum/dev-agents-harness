---
name: dockerfile-hardening
description: Review a Dockerfile or image against CIS Docker Benchmark and modern supply-chain practice, and emit a hardened replacement. Use on Dockerfile PRs or image audits.
user-invocable: true
---

# Dockerfile Hardening

## Objective
Reduce image attack surface and supply-chain risk while keeping the build working.

## Procedure
1. Pin the base image to an immutable digest, not a floating tag.
2. Convert to multi-stage build; keep only runtime artifacts in the final image.
3. Add an explicit non-root `USER`; prefer a read-only root filesystem.
4. Check for secrets in build-args, ENV, or layers; remove and route through a secret store.
5. Verify no unnecessary packages (shells, curl, compilers) in the final stage.
6. Emit the hardened multi-stage Dockerfile.

## Rules
- Do not break the app's runtime requirements; note any change that alters behavior.
- Cite the CIS Docker Benchmark or OWASP guidance for each change.

## Output
Findings (severity, evidence, standard cited) · Hardened Dockerfile · Notes on behavior changes.
