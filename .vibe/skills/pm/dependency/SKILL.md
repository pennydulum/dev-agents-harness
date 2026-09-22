---
name: dependency
description: Identify, document, and manage dependencies between work items.
user-invocable: true
---

# Dependency Skill

Use this skill when:
- Identifying a new Dependency.
- Documenting an existing Dependency.
- Reviewing Dependencies for completeness.

---

## Required Fields
Every Dependency must include:
1. **Source**: What is the source of this Dependency?
2. **Target**: What does this Dependency affect?
3. **Relationship**: `blocks` / `blocked-by` / `depends-on` / `enables`
4. **Reason**: Why does this Dependency exist?
5. **Owner**: Who is responsible for resolving this Dependency?
6. **Status**: `OPEN` / `RESOLVED` / `BLOCKED`
7. **Required-by Date**: When does this Dependency need to be resolved?
8. **Risk**: `LOW` / `MEDIUM` / `HIGH` / `CRITICAL`
9. **Mitigation**: How can this Dependency be resolved or mitigated?

---

## Process
1. **Identify Source and Target**:
   - What is the source of this Dependency?
   - What does it affect?
2. **Define Relationship**:
   - Does it `block`, `blocked-by`, `depends-on`, or `enables`?
3. **Document Reason**:
   - Why does this Dependency exist?
4. **Assign Ownership**:
   - Who is responsible for resolving this Dependency?
5. **Assess Risk**:
   - What is the risk if this Dependency is not resolved?
6. **Define Mitigation**:
   - How can this Dependency be resolved or mitigated?
7. **Set Required-by Date**:
   - When does this Dependency need to be resolved?
8. **Review**:
   - Is the Dependency **clearly documented**?
   - Are all **fields** complete?

---

## Quality Checks
**Reject or flag Dependencies that**:
- Lack a clear **source** or **target**.
- Have **no relationship** defined.
- Have **no owner** or **required-by date**.
- Lack **mitigation** for high-risk Dependencies.

---

## Template
Use the template from `.vibe/agents/pm-agent/templates/dependency.md`.