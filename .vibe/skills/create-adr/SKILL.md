---
name: create-adr
description: Write an Architecture Decision Record from a decision, discussion, or proposal. Use when a significant technical decision is made or proposed.
user-invocable: true
---

# Create ADR

## Procedure
1. Find the next ADR number in docs/adr/.
2. Gather context from the repo and the conversation. Do not invent facts.
3. Record real alternatives, including "do nothing".
4. Write the ADR using the template in docs/adr/TEMPLATE.md. Status starts as Proposed.
5. Link related ADRs. If this supersedes one, update the old ADR's status.

## Output
A single file docs/adr/adr-XXXX-<slug>.md following the template exactly.
