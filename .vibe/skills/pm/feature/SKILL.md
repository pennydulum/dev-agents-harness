---
name: feature
description: Create, refine, and decompose Features into Stories and Tasks.
user-invocable: true
---

# Feature Skill

Use this skill when:
- Creating a new Feature.
- Refining an existing Feature.
- Decomposing a Feature into Stories/Tasks.
- Reviewing a Feature for completeness.

---

## Required Fields
Every Feature must include:
1. **Name**: Clear, concise title.
2. **Capability**: What capability are we delivering?
3. **Who Uses It?**: Who is the target user?
4. **Why Does It Matter?**: Why is this feature important?
5. **Expected Behavior**: What behavior is expected?
6. **Out of Scope**: What is explicitly excluded?
7. **Acceptance Criteria**: How will we know the Feature is complete?
8. **Dependencies**: What blocks this Feature?
9. **Owner**: Who is responsible for this Feature?

---

## Process
1. **Understand the Capability**:
   - What capability are we delivering?
2. **Identify the User**:
   - Who will use this Feature?
3. **Identify the Value**:
   - Why does this Feature matter?
4. **Define Expected Behavior**:
   - What should this Feature do?
5. **Identify Scope**:
   - What is included?
   - What is explicitly excluded?
6. **Identify Acceptance Criteria**:
   - How will we know the Feature is complete?
7. **Identify Dependencies**:
   - What blocks this Feature?
8. **Assign Ownership**:
   - Who is responsible for this Feature?
9. **Review**:
   - Is the Feature **appropriately sized**?
   - Are all **dependencies** identified?

---

## Quality Checks
**Reject or flag Features that**:
- Lack a clear **capability** or **user**.
- Have **no acceptance criteria**.
- Contain **multiple unrelated capabilities**.
- Depend on **undefined external work**.
- Use **ambiguous terms** without definitions.

---

## Template
Use the template from `.vibe/agents/pm-agent/templates/feature.md`.