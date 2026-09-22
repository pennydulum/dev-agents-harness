---
name: bug
description: Create, refine, and manage Bug reports.
user-invocable: true
---

# Bug Skill

Use this skill when:
- Reporting a new Bug.
- Refining an existing Bug report.
- Reviewing a Bug for completeness.

---

## Required Fields
Every Bug must include:
1. **Name**: Clear, concise title.
2. **Summary**: Brief description of the Bug.
3. **Expected Behavior**: What should happen?
4. **Actual Behavior**: What is happening instead?
5. **Reproduction Steps**: How can this Bug be reproduced?
6. **Environment**: OS, Browser, Version, etc.
7. **Severity**: `LOW` / `MEDIUM` / `HIGH` / `CRITICAL`
8. **Impact**: What is the impact of this Bug?
9. **Frequency**: `Always` / `Often` / `Sometimes` / `Rarely`
10. **Evidence**: Screenshots, logs, etc.
11. **Suspected Area**: Where do you think the issue is?
12. **Workaround**: Is there a temporary workaround?
13. **Regression Information**: When was this Bug introduced?
14. **Fix Criteria**: How will we know the Bug is fixed?
15. **Owner**: Who is responsible for fixing this Bug?

---

## Process
1. **Reproduce the Bug**:
   - Can the Bug be reproduced?
2. **Document Expected Behavior**:
   - What should happen?
3. **Document Actual Behavior**:
   - What is happening instead?
4. **Identify Reproduction Steps**:
   - How can this Bug be reproduced?
5. **Identify Environment**:
   - OS, Browser, Version, etc.
6. **Assess Severity and Impact**:
   - How severe is this Bug?
   - What is the impact?
7. **Identify Frequency**:
   - How often does this Bug occur?
8. **Gather Evidence**:
   - Screenshots, logs, etc.
9. **Identify Suspected Area**:
   - Where do you think the issue is?
10. **Identify Workaround**:
    - Is there a temporary workaround?
11. **Identify Regression Information**:
    - When was this Bug introduced?
12. **Define Fix Criteria**:
    - How will we know the Bug is fixed?
13. **Assign Ownership**:
    - Who is responsible for fixing this Bug?

---

## Quality Checks
**Reject or flag Bugs that**:
- Lack **reproduction steps** or **expected behavior**.
- Have **no severity or impact** assessment.
- Are **unreproducible**.
- Lack **evidence** (screenshots, logs, etc.).

---

## Template
Use the template from `.vibe/agents/pm-agent/templates/bug.md`.