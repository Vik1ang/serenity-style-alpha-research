# Agent Integration Guide

This repository is an agent-usable research skill package. The canonical artifact is `skills/structural-alpha-research/`; platform-specific files are adapters that tell each agent how to load and apply that canonical skill.

## Canonical Source

Use `skills/structural-alpha-research/` as the source of truth for all agents. It contains:

- `SKILL.md` — activation rules, hard constraints, and core workflow.
- `references/output-template.md` — full memo, shortlist, compact triage, and trading-scenario output skeleton.
- `references/trading-scenario.md` — non-advisory trading-scenario status mapping, upgrade/downgrade rules, checkpoints, triggers, invalidation, and risk controls.
- `references/cycle-objectivity-overlay.md` — cycle, comparative-advantage, low-base elasticity, liquidity, and objectivity overlay inspired by global-cycle / objectivity method synthesis.
- `docs/decisions/` — validation baskets, maintenance decisions, and peer-discussion records; these are not runtime recommendations.
- `references/a-share-skill-spec-FINAL.md` — A-share top-level read path.
- R4/R5/R6 reference files — A-share thesis-level bucketing, company-level red flags, and market-structure evidence.
- R9/R10 reference files — Biotech BD income quality and qualifying large-cap residual re-rating.

Do not edit only a hidden local install copy. Make methodology changes in `skills/` first, then sync any local mirrors.

## Agent Surfaces

### Codex / OpenAI

- Project-level runtime mirror: `.codex/skills/structural-alpha-research/`
- Canonical source: `skills/structural-alpha-research/`
- UI metadata: `skills/structural-alpha-research/agents/openai.yaml`

When changing the skill, keep `skills/` and `.codex/skills/` byte-for-byte synchronized.

### Claude Code

Claude Code should read `CLAUDE.md` first. That file points Claude to the canonical skill and preserves the hard rules. Claude should then load:

1. `skills/structural-alpha-research/SKILL.md`
2. `references/output-template.md` for output shape
3. `references/trading-scenario.md` for trading-scenario requests
4. `references/cycle-objectivity-overlay.md` when global cycle / objectivity / low-base elasticity is central
5. `references/a-share-skill-spec-FINAL.md`, R4/R5/R6 as the base, and R9/R10 only when their specialist conditions apply

Claude should not rely on `.codex/` as its source of truth.

### Gemini CLI / Other Markdown-Aware Agents

Gemini and other agents should read `GEMINI.md` or `AGENTS.md`, then load the same canonical skill files under `skills/`. If an agent has no native skill loader, use the repository as a reference package: load `SKILL.md` plus the minimum relevant reference files.

### Generic Chat LLMs

For agents without filesystem access, paste or attach:

1. `skills/structural-alpha-research/SKILL.md`
2. `references/output-template.md`
3. For trading-scenario requests, `references/trading-scenario.md`
4. For global-cycle / objectivity augmentation, `references/cycle-objectivity-overlay.md`
5. For A-share research, `references/a-share-skill-spec-FINAL.md` plus only the required R4/R5/R6/R9/R10 files

Avoid pasting all A-share provenance files unless doing methodology review.

## Cross-Agent Invariants

Every agent must preserve these rules:

- Default output language is Chinese unless the user asks otherwise.
- No A/B/C/D ratings; use textual conclusion states and confidence.
- No direct buy/sell/position-size/target/stop advice.
- Trading scenario output must follow `references/trading-scenario.md` and is allowed only as non-advisory status, checkpoints, triggers, invalidation, and risk controls.
- Social-media-only evidence cannot support a strong alpha conclusion.
- Missing cycle proof, demand proof, bottleneck proof, comparative advantage, materiality, market context, or risk checks means Watchlist / Excluded, not Shortlist.
- When validating the skill itself, use mixed samples: likely positives, crowded winners, exposure-impure cases, and red-flag false positives. Store the results in `docs/decisions/`, not `references/`.
- Method simulations inspired by external frameworks must be labeled as inference and must not be presented as source-attributed views without loaded source evidence.
- A-share work starts from the A-share FINAL index, not from a direct US-to-A-share gate translation.

## Maintenance Rule

When updating behavior, update in this order:

1. `skills/structural-alpha-research/SKILL.md` or the owning `references/` file.
2. Root agent docs if the change affects usage: `README.md`, `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`.
3. `.codex/skills/structural-alpha-research/` local mirror if the canonical skill changed.
4. Verify references and mirror consistency before committing.

Maintenance candidates, action plans, and peer-discussion live under `docs/decisions/` and must not be loaded as runtime research references.
