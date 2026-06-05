# AGENTS.md

Guidance for OpenAI/Codex-style agents and other coding agents working in this repository.

## Repository Role

This repository is a Markdown skill/reference package for Serenity-style alpha research. It is not a runnable application. There is no build, test, or service process.

Canonical skill source:

- `skills/serenity-style-alpha-research/SKILL.md`
- `skills/serenity-style-alpha-research/references/`

The `.codex/skills/serenity-style-alpha-research/` directory is only the local Codex project-level install mirror. Do not treat hidden install mirrors as the canonical source.

## How To Use The Skill

For stock-selection, chokepoint alpha, A-share thesis-level research, or non-advisory trading-scenario analysis:

1. Load `skills/serenity-style-alpha-research/SKILL.md`.
2. Load `references/output-template.md` when the user asks for a full memo, shortlist, or trading-scenario output.
3. For A-share work, start with `references/a-share-skill-spec-FINAL.md`; then load R4/R5/R6 detail files only as needed.

## Hard Rules

- Default output language is Chinese unless explicitly changed.
- Do not use A/B/C/D ratings.
- Do not provide direct buy/sell/position-size/target/stop advice.
- If asked for trading advice, use the non-advisory 交易推演 layer: status, checkpoints, triggers, invalidation, and risk controls.
- Social-media-only evidence is never enough for a strong alpha conclusion.
- Missing demand proof, bottleneck proof, materiality, market context, or risk checks means Watchlist / Excluded, not Shortlist.

## Editing Rules

- Edit canonical files under `skills/` first.
- Keep `.codex/skills/serenity-style-alpha-research/` synchronized after canonical skill changes.
- Update `README.md`, `CLAUDE.md`, `GEMINI.md`, and `docs/agent-integration.md` when behavior or installation guidance changes.
- Do not add application scaffolding (`package.json`, build tooling, CI) unless explicitly requested.
