# GEMINI.md

## Reference index

- **A 股总入口** — `skills/structural-alpha-research/references/a-share-skill-spec-FINAL.md`
- **R9 / Biotech BD 收入质量** — `skills/structural-alpha-research/references/a-share-r9-biotech-bd-quality.md`
- **R10 / 大市值剩余重估空间** — `skills/structural-alpha-research/references/a-share-r10-large-cap-rerating-residual.md`
- **周期/客观性增强层** — `skills/structural-alpha-research/references/cycle-objectivity-overlay.md`
- **完整跑票与复盘样本** — `skills/structural-alpha-research/references/a-share-worked-examples.md`

Guidance for Gemini CLI and other Markdown-aware agents using this repository.

## What To Load

This repository is an agent-usable research skill package. Use the canonical skill files, not the Codex mirror:

1. `skills/structural-alpha-research/SKILL.md`
2. `skills/structural-alpha-research/references/output-template.md` when output structure matters
3. `skills/structural-alpha-research/references/trading-scenario.md` when the user asks for trading scenario analysis
4. `skills/structural-alpha-research/references/a-share-skill-spec-FINAL.md` for A-share work
5. `skills/structural-alpha-research/references/cycle-objectivity-overlay.md` when combining structural alpha with global-cycle / objectivity / low-base elasticity methods
6. `docs/decisions/` validation notes only when reviewing the skill itself; do not treat validation tickers as runtime recommendations
6. R4/R5/R6 reference files for the A-share base; R9 for Biotech BD; R10 for large-cap residual re-rating

See `docs/agent-integration.md` for the full cross-agent map.

## Behavior To Preserve

- Output Chinese by default.
- Use textual conclusion states, not A/B/C/D ratings.
- Do not give direct buy/sell/position-size/target/stop advice.
- If the user asks “怎么交易 / 买不买 / 能不能做”, load `references/trading-scenario.md` and output a non-advisory 交易推演: current status, checkpoints, triggers, invalidation, and risk controls.
- Do not let social-media evidence alone support a strong alpha conclusion.
- Do not attribute a method simulation to any external source unless loaded primary-source evidence supports it.
- For A-share research, use thesis-level bucketing and the A-share FINAL index; do not mechanically translate US-market gates. A-share shortlist work must include a dated market snapshot and R2/R3/crowding judgment when data exists; no coverage means data insufficient, not risk cleared.

## Maintenance

If you change methodology, edit `skills/structural-alpha-research/` first and update root agent docs if the usage contract changes. `.codex/` is only a local Codex mirror. Keep planning, validation baskets, and peer-discussion under `docs/decisions/`, outside runtime references.
