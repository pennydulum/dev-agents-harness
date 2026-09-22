# Agent Instructions — dev-agents-harness

## Purpose
Shared harness for team agents (Orion + future agents). Config, prompts, skills, knowledge library, and ADRs live here.

## Rules for every agent in this repo

- **Read before writing.** Inspect `.vibe/`, `docs/adr/`, and recent commits before proposing changes.
- **Skills follow the Agent Skills spec:** one folder per skill, `SKILL.md` with YAML frontmatter (`name`, `description`, `user-invocable`).
- **Agent definitions must declare `agent_type = "agent"`.** `system_prompt_id` points at `.vibe/prompts/<id>.md`.
- **The `safety` field is cosmetic** (border color). Real control = per-tool `permission = "ask" | "always"` and `disabled_tools`.
- **Scheduled/unattended runs** must pass `--agent` explicitly (programmatic mode falls back to auto-approve otherwise). Use `orion-audit` for scheduled jobs.
- **Library entries** need the metadata header (title, source, url, authority, version, last_verified). One page max, link to the original, no wholesale copies.
- **Never commit secrets**, tokens, `.env` files, cookies, or browser profile data.
- **ADR before structural change.** Significant decisions get an ADR in `docs/adr/` using the standard template.

## Commands

```bash
# run orion
vibe --agent orion

# read-only audit run
vibe --agent orion-audit -p "<prompt>"

# validate TOML syntax quickly
npx @taplo/cli fmt --check .vibe/**/*.toml
```

## Do Not

- Never force-push to `main`.
- Never edit another agent's prompt or toml without coordinating in an issue first.
- Never add a connector/tool permission wider than the task requires.
