---
title: OWASP Top 10 2025
source: OWASP
url: https://owasp.org/Top10/2025/
authority: High
version: 1.0
last_verified: 2026-09-23
---

# OWASP Top 10: 2025

## Overview
The **OWASP Top 10** is a standard awareness document for developers and security practitioners. The **2025 edition** reflects the latest risks in modern applications.

## Categories
| Rank | Category                          | Description                                                                 | QA Testing Focus                          |
|------|-----------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| A01  | Broken Access Control             | Unauthorized access to data/functionality.               | Tenant isolation, RBAC, permission checks. |
| A02  | Security Misconfiguration         | Default configs, verbose errors, exposed debug endpoints. | Hardened CI/CD, least-privilege connectors. |
| A03  | Software Supply Chain Failures    | Vulnerable dependencies, compromised builds.             | SBOM, SLSA provenance, dependency scanning. |
| A04  | Cryptographic Failures            | Weak algorithms, hardcoded secrets, poor randomness.       | No hardcoded secrets, modern crypto.      |
| A05  | Injection                         | SQL, NoSQL, OS, LDAP injection.                            | Zod validation, Prisma parameterized queries. |
| A06  | Insecure Design                  | Missing security controls by design.                     | Threat modeling, secure defaults.        |
| A07  | Authentication Failures           | Weak session management, credential stuffing.           | Okta PKCE testing, session management.    |
| A08  | Software/Data Integrity Failures  | Code or infrastructure tampering.                        | Checksums, signed artifacts.              |
| A09  | Security Logging & Alerting Failures | Insufficient logging or monitoring.                     | Structured logs, no sensitive data.       |
| A10  | Mishandling of Exceptional Conditions | Errors expose stack traces or sensitive data.       | Safe error messages, no stack traces.    |

## ASVS 5.0 Alignment
- **L1 (Baseline)**: All projects.
- **L2 (Standard)**: Business-critical apps (recommended for most projects).
- **L3 (Advanced)**: High-risk (finance, healthcare).

## QA Checklist
- [ ] **A01**: Test tenant isolation (e.g., "Tenant A cannot access Tenant B’s data").
- [ ] **A02**: Verify no debug endpoints are exposed in production.
- [ ] **A03**: Scan dependencies (`pnpm audit`, `snyk`).
- [ ] **A04**: No hardcoded secrets in code or configs.
- [ ] **A05**: Use Zod for input validation; Prisma for parameterized queries.
- [ ] **A06**: Threat model new features.
- [ ] **A07**: Test auth flows (Okta PKCE, session timeouts).
- [ ] **A08**: Validate artifact signatures (SLSA).
- [ ] **A09**: Structured logs with correlation IDs.
- [ ] **A10**: Safe error messages (no stack traces in production).

## Resources
- [OWASP Top 10 2025](https://owasp.org/Top10/2025/)
- [OWASP ASVS 5.0](https://owasp.org/www-project-application-security-verification-standard/)