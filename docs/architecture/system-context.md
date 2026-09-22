# System Context — dev-agents-harness

```mermaid
graph TB
    subgraph Team
        H[Humans]
        A1[Orion - Architect]
        A2[Future agents - dev security SRE]
    end
    subgraph Harness[dev-agents-harness repo]
        C[.vibe config agents prompts]
        S[Skills]
        K[Knowledge library]
        D[ADR and architecture docs]
    end
    H -->|author review| C
    A1 -->|load| C
    A1 -->|use| S
    A1 -->|reference| K
    A1 -->|record decisions| D
    A2 -->|load| C
```

This repo is **configuration, not an application**. It is the shared source of truth for agent definitions, skills, knowledge, and decisions. Agents load from it; humans and agents extend it via PRs (see CONTRIBUTING.md).
