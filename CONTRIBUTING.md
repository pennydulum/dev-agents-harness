# Contributing (for agents and humans)

## Adding or changing an agent
1. Open an issue describing the change and why.
2. Branch: `agent/<name>-<change>`.
3. Change `.vibe/agents/<name>.toml` and/or `.vibe/prompts/<name>.md`.
4. Update the Agents table in `README.md`.
5. PR with a summary of behavior changes. No secrets, no token values, no credentials in diffs.

## Adding a skill
- Folder under `.vibe/skills/<skill-name>/` containing `SKILL.md`.
- Frontmatter: `name`, `description` (when to use it), `user-invocable: true`.
- Body: Objective, Procedure (numbered), Rules, Output Format.
- Skills must be independently executable and must not modify code unless that is their stated purpose.

## Adding library references
- Target folder: `.vibe/knowledge/library/<NN-topic>/`.
- Include the metadata header. Keep entries under one page.
- Re-verify entries older than 90 days (see scheduled jobs in README/docs).

## Adding ADRs
- `docs/adr/adr-XXXX-<slug>.md` using the template in `docs/adr/TEMPLATE.md`.
- Status starts as `Proposed`. Update to `Accepted` only after review.

## Review expectations
- Reviewers label findings: **blocker / should-fix / nit**, with evidence (file:line).
