# PM Agent — Abbey

This directory contains the **Project Manager (PM) Agent (Abbey)** specification, including its **identity, expertise, workflows, and operating principles**. Abbey specializes in **project management**, including **Epics, Stories, Features, Tasks, Bugs, and Dependencies**.

---

## Directory Structure
```text
.vibe/agents/pm-agent/
├── AGENT.md          # Master profile for Abbey
├── README.md         # This file
├── templates/        # Reusable templates for PM artifacts
│   ├── epic.md
│   ├── feature.md
│   ├── story.md
│   ├── task.md
│   ├── bug.md
│   ├── dependency.md
│   ├── decision.md
│   └── status-report.md
└── adapters/         # Harness-specific configurations (if needed)
```

---

## Usage
### **Mistral Vibe CLI**
To use Abbey in Mistral Vibe CLI:
```bash
vibe --agent project-manager
```

### **Mistral Vibe Web App**
1. Ensure the `.vibe/` directory is synced with your Mistral Vibe workspace.
2. Select the **Abbey — Project Manager** agent from the list of available agents.

---

## Key Features
- **Work Breakdown**: Decomposes objectives into **Epics → Features → Stories → Tasks**.
- **Dependency Management**: Identifies and tracks **hard/soft dependencies**.
- **Risk Management**: Proactively identifies and mitigates risks.
- **Stakeholder Communication**: Provides **clear, actionable updates**.
- **Traceability**: Maintains alignment between **business objectives, product requirements, and engineering implementation**.

---

## Agent Configuration
- **Agent Config**: `.vibe/agents/project-manager.toml`
- **System Prompt**: `.vibe/prompts/project-manager.md`

---

## Shared Resources
- **Skills**: `.vibe/skills/pm/` (e.g., `epic/SKILL.md`, `story/SKILL.md`)
- **Knowledge**: `.vibe/knowledge/` (e.g., `pm.md`, `delivery.md`)
- **Library**: `.vibe/library/` (e.g., `agile/scrum-guide.md`)

---

## Contributing
To add or update Abbey's capabilities:
1. **Skills**: Add new skills to `.vibe/skills/pm/`.
2. **Templates**: Add or update templates in `.vibe/agents/pm-agent/templates/`.
3. **Knowledge**: Expand the knowledge base in `.vibe/knowledge/`.
4. **Library**: Add reference materials to `.vibe/library/`.

---

## License
This agent specification is part of the **dev-agents-harness** repository and is licensed under the same terms as the parent repository.