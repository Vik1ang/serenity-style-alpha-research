# AGENTS.md

Guidance for OpenAI/Codex-style agents and other coding agents working in this repository.

## Repository Role

This repository is a Markdown skill/reference package for structural alpha research: supply-chain bottleneck validation plus a global-cycle, objectivity, liquidity, and low-base elasticity overlay. It is not a runnable application. There is no build, test, or service process.

Canonical skill source:

- `skills/structural-alpha-research/SKILL.md`
- `skills/structural-alpha-research/references/`

The `.codex/skills/structural-alpha-research/` directory is only the local Codex project-level install mirror. Do not treat hidden install mirrors as the canonical source.

## How To Use The Skill

For stock-selection, chokepoint alpha, cycle/technology-inflation thesis validation, A-share thesis-level research, or non-advisory trading-scenario analysis:

1. Load `skills/structural-alpha-research/SKILL.md`.
2. Load `references/output-template.md` when the user asks for a full memo, shortlist, or trading-scenario output.
3. Load `references/trading-scenario.md` when the user asks “怎么交易 / 能不能做 / 买不买 / 卖不卖 / 交易推演”.
4. Load `references/cycle-objectivity-overlay.md` when the task asks to combine structural alpha with global-cycle / objectivity methods, or when cycle proof / comparative advantage / low-ROE elasticity / liquidity objectivity is central.
5. For A-share work, start with `references/a-share-skill-spec-FINAL.md`; load R4/R5/R6 as the base, R9 for Biotech BD, and R10 for qualifying large-cap re-rating work.

## Hard Rules

- Default output language is Chinese unless explicitly changed.
- Do not use A/B/C/D ratings.
- Do not provide direct buy/sell/position-size/target/stop advice.
- If asked for trading advice, use `references/trading-scenario.md` and output the non-advisory 交易推演 layer: status, checkpoints, triggers, invalidation, and risk controls.
- Social-media-only evidence is never enough for a strong alpha conclusion.
- Missing cycle proof, demand proof, bottleneck proof, comparative advantage, materiality, market context, or risk checks means Watchlist / Excluded, not Shortlist.

## Editing Rules

- Edit canonical files under `skills/` first.
- Keep `.codex/skills/structural-alpha-research/` synchronized after canonical skill changes.
- Update `README.md`, `CLAUDE.md`, `GEMINI.md`, and `docs/agent-integration.md` when behavior or installation guidance changes.
- Keep benchmark candidates, action plans, and peer-discussion in `docs/decisions/`, not runtime `references/`.
- Do not add application scaffolding (`package.json`, build tooling, CI) unless explicitly requested.
