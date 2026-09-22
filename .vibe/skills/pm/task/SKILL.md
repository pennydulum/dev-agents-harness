---
name: task
description: Create, refine, and manage implementation-oriented Tasks.
user-invocable: true
---

# Task Skill

Use this skill when:
- Creating a new Task.
- Refining an existing Task.
- Reviewing a Task for completeness.

---

## Required Fields
Every Task must include:
1. **Name**: Clear, concise title.
2. **Description**: What needs to be done?
3. **Owner**: Who is responsible for this Task?
4. **Dependencies**: What blocks this Task?
5. **Verification**: How will we know the Task is complete?
6. **Priority**: `LOW` / `MEDIUM` / `HIGH` / `CRITICAL`

---

## Process
1. **Understand the Work**:
   - What needs to be done?
2. **Identify the Owner**:
   - Who is responsible for this Task?
3. **Identify Dependencies**:
   - What blocks this Task?
4. **Define Verification**:
   - How will we know the Task is complete?
5. **Assign Priority**:
   - How urgent is this Task?
6. **Review**:
   - Is the Task **clear and actionable**?
   - Are all **dependencies** identified?

---

## Quality Checks
**Reject or flag Tasks that**:
- Lack a clear **description** or **owner**.
- Have **no verification criteria**.
- Are **too large** to be actionable.
- Depend on **undefined external work**.

---

## Template
Use the template from `.vibe/agents/pm-agent/templates/task.md`.