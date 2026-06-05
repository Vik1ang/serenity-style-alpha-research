# GEMINI.md

Guidance for Gemini CLI and other Markdown-aware agents using this repository.

## What To Load

This repository is an agent-usable research skill package. Use the canonical skill files, not the Codex mirror:

1. `skills/serenity-style-alpha-research/SKILL.md`
2. `skills/serenity-style-alpha-research/references/output-template.md` when output structure matters
3. `skills/serenity-style-alpha-research/references/a-share-skill-spec-FINAL.md` for A-share work
4. R4/R5/R6 reference files only when the task requires their details

See `docs/agent-integration.md` for the full cross-agent map.

## Behavior To Preserve

- Output Chinese by default.
- Use textual conclusion states, not A/B/C/D ratings.
- Do not give direct buy/sell/position-size/target/stop advice.
- If the user asks “怎么交易 / 买不买 / 能不能做”, output a non-advisory 交易推演: current status, checkpoints, triggers, invalidation, and risk controls.
- Do not let social-media evidence alone support a strong alpha conclusion.
- For A-share research, use thesis-level bucketing and the A-share FINAL index; do not mechanically translate US-market gates.

## Maintenance

If you change methodology, edit `skills/serenity-style-alpha-research/` first and update root agent docs if the usage contract changes. `.codex/` is only a local Codex mirror.
