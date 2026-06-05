# Agent Integration Guide

This repository is an agent-usable research skill package. The canonical artifact is `skills/serenity-style-alpha-research/`; platform-specific files are adapters that tell each agent how to load and apply that canonical skill.

## Canonical Source

Use `skills/serenity-style-alpha-research/` as the source of truth for all agents. It contains:

- `SKILL.md` — activation rules, hard constraints, and core workflow.
- `references/output-template.md` — full memo, shortlist, compact triage, and non-advisory trading-scenario output.
- `references/a-share-skill-spec-FINAL.md` — A-share top-level read path.
- R4/R5/R6 reference files — thesis-level bucketing, announcement counter-evidence, company-level red flags, and market-structure evidence.

Do not edit only a hidden local install copy. Make methodology changes in `skills/` first, then sync any local mirrors.

## Agent Surfaces

### Codex / OpenAI

- Project-level runtime mirror: `.codex/skills/serenity-style-alpha-research/`
- Canonical source: `skills/serenity-style-alpha-research/`
- UI metadata: `skills/serenity-style-alpha-research/agents/openai.yaml`

When changing the skill, keep `skills/` and `.codex/skills/` byte-for-byte synchronized.

### Claude Code

Claude Code should read `CLAUDE.md` first. That file points Claude to the canonical skill and preserves the hard rules. Claude should then load:

1. `skills/serenity-style-alpha-research/SKILL.md`
2. `references/output-template.md` for output shape
3. `references/a-share-skill-spec-FINAL.md` and R4/R5/R6 detail files for A-share work

Claude should not rely on `.codex/` as its source of truth.

### Gemini CLI / Other Markdown-Aware Agents

Gemini and other agents should read `GEMINI.md` or `AGENTS.md`, then load the same canonical skill files under `skills/`. If an agent has no native skill loader, use the repository as a reference package: load `SKILL.md` plus the minimum relevant reference files.

### Generic Chat LLMs

For agents without filesystem access, paste or attach:

1. `skills/serenity-style-alpha-research/SKILL.md`
2. `references/output-template.md`
3. For A-share research, `references/a-share-skill-spec-FINAL.md` plus the specific R4/R5/R6 file required by the task

Avoid pasting all A-share provenance files unless doing methodology review.

## Cross-Agent Invariants

Every agent must preserve these rules:

- Default output language is Chinese unless the user asks otherwise.
- No A/B/C/D ratings; use textual conclusion states and confidence.
- No direct buy/sell/position-size/target/stop advice.
- Trading scenario output is allowed only as non-advisory status, checkpoints, triggers, invalidation, and risk controls.
- Social-media-only evidence cannot support a strong alpha conclusion.
- Missing demand proof, bottleneck proof, materiality, market context, or risk checks means Watchlist / Excluded, not Shortlist.
- A-share work starts from the A-share FINAL index, not from a direct US-to-A-share gate translation.

## Maintenance Rule

When updating behavior, update in this order:

1. `skills/serenity-style-alpha-research/SKILL.md` or the owning `references/` file.
2. Root agent docs if the change affects usage: `README.md`, `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`.
3. `.codex/skills/serenity-style-alpha-research/` local mirror if the canonical skill changed.
4. Verify references and mirror consistency before committing.
