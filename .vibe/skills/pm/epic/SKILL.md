---
name: epic
description: Create, refine, and decompose Epics into Features and Stories.
user-invocable: true
---

# Epic Skill

Use this skill when:
- Creating a new Epic.
- Refining an existing Epic.
- Decomposing an Epic into Features/Stories.
- Reviewing an Epic for completeness.

---

## Required Fields
Every Epic must include:
1. **Name**: Clear, concise title.
2. **Problem**: The problem this Epic solves.
3. **Objective**: The desired outcome.
4. **Scope**: What is included.
5. **Out of Scope**: What is explicitly excluded.
6. **Success Criteria**: Measurable outcomes.
7. **Features**: List of Features under this Epic.
8. **Dependencies**: External or internal dependencies.
9. **Risks**: Potential risks and mitigations.
10. **Assumptions**: Key assumptions.
11. **Milestone**: Target timeline.
12. **Owner**: Responsible person/team.

---

## Process
1. **Understand the Objective**:
   - What problem does this Epic solve?
   - Who benefits?
   - What does success look like?

2. **Define Scope**:
   - What is included?
   - What is explicitly excluded?

3. **Identify Features**:
   - Break the Epic into **coherent Features**. 
   - Each Feature should deliver a **specific capability**.

4. **Identify Dependencies**:
   - What blocks this Epic?
   - What does this Epic block?

5. **Identify Risks**:
   - What could go wrong?
   - How can risks be mitigated?

6. **Define Success Criteria**:
   - How will we know the Epic is complete?

7. **Assign Ownership**:
   - Who is responsible for this Epic?

8. **Review**:
   - Is the Epic **appropriately sized**?
   - Are all **dependencies** identified?
   - Are **acceptance criteria** clear?

---

## Quality Checks
**Reject or flag Epics that**:
- Lack a clear **objective** or **problem statement**.
- Have **no success criteria**.
- Contain **multiple unrelated outcomes**.
- Depend on **undefined external work**.
- Use **ambiguous terms** without definitions.

---

## Template
Use the template from `.vibe/agents/pm-agent/templates/epic.md`.