---
name: threat-model
description: Build a threat model with trust boundaries, data flows, and prioritized mitigations. Use for new features, integrations, or security reviews.
user-invocable: true
---

# Threat Model

## Procedure
1. Define scope and assets (data, credentials, availability, reputation).
2. Draw a data-flow diagram in Mermaid with trust boundaries.
3. For each flow and component, apply STRIDE: spoofing, tampering, repudiation, information disclosure, denial of service, elevation of privilege.
4. For multi-tenant systems, add tenant-isolation threats across data, jobs, caches, storage, search, logs, exports, and admin access.
5. Rate each threat by likelihood and impact.
6. Propose mitigations mapped to OWASP ASVS requirements where applicable.
7. List residual risk and what would change the assessment.

## Output
Scope · Assets · Diagram · Threat table (ID, threat, category, likelihood, impact, mitigation, status) · Residual risks · Follow-ups
