---
name: story
description: Create, refine, review, and decompose user stories into testable delivery units.
user-invocable: true
---

# Story Skill

Use this skill when creating, reviewing, refining, or decomposing user stories.

---

## Required Fields
Every Story must include:
- **User/Value Statement**: `As a [user], I want [capability], so that [outcome].`
- **Context**: Additional context for the story.
- **Acceptance Criteria**: Given/When/Then format.
- **Dependencies**: What blocks this story?
- **Edge Cases**: Any edge cases to consider.
- **Definition of Done**: What does "done" look like?

---

## Process
1. **Understand the Outcome**:
   - What is the desired outcome?
2. **Identify the User**:
   - Who is the target user?
3. **Identify the Capability**:
   - What capability are we delivering?
4. **Identify Acceptance Criteria**:
   - How will we know the story is complete?
5. **Identify Dependencies**:
   - What blocks this story?
6. **Identify Ambiguity**:
   - Are there any unclear requirements?
7. **Identify Edge Cases**:
   - What edge cases need to be addressed?
8. **Determine Size**:
   - Is the story appropriately sized?
9. **Produce the Story**:
   - Write the final story with all required fields.

---

## Quality Checks
**Reject or flag Stories that**:
- Contain **multiple unrelated outcomes**.
- Have **no measurable acceptance criteria**.
- Hide **major technical projects** inside one story.
- Depend on **undefined external work**.
- Use **ambiguous terms** without definitions.

---

## Template
Use the template from `.vibe/agents/pm-agent/templates/story.md`.