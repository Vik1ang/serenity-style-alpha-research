# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

This is a **Codex / OpenAI skill package**, not a runnable application. There is
no `package.json`, no build step, no test suite. The shipped artifact is the
skill at `.codex/skills/serenity-style-alpha-research/` plus its
`references/` directory; agents load `SKILL.md` (with frontmatter) at runtime
and follow its behavioral rules.

Subject domain: Serenity-style "chokepoint alpha" stock screening — supply
chain bottlenecks in AI / semiconductor / datacenter-power chains, evaluated
through five factors (Certain Demand, Constrained Supply, Low Attention,
Value Capture, Catalyst) plus an Anti-Thesis check.

## Key Files

- `.codex/skills/serenity-style-alpha-research/SKILL.md` — entry point.
  Contains YAML frontmatter (`name`, `description`,
  `metadata.short-description`) plus the full behavioral spec (workflow,
  shortlist gate, evidence hierarchy, conclusion states, hard caps). **Do
  not strip the frontmatter** — agents use it to decide whether to trigger
  the skill.
- `.codex/skills/serenity-style-alpha-research/references/output-template.md`
  — full research memo and shortlist format. Use this when the user asks
  for a deep dive or stock screen.
- `.codex/skills/serenity-style-alpha-research/references/domain-extensions.md`
  — AI / semi / DC-power / crypto-mining-to-HPC / A·H·HK·US supply-chain
  variants.
- `.codex/skills/serenity-style-alpha-research/references/scoring.md` —
  elasticity math + factor checklist. **Do not** use this to produce
  A/B/C/D ratings; only for quantitative work.
- `.codex/skills/serenity-style-alpha-research/references/a-share-skill-spec-draft.md`
  — A-share-specific draft spec.

## Hard Rules (Preserve When Editing)

These are enforced inside `SKILL.md` and must not be weakened:

- **No A/B/C/D ratings.** Use only the four textual conclusion states:
  `强 Alpha 候选（需持续验证）` / `有潜力，但关键数据待验证` / `更像主题叙事`
  / `暂时否定或回避研究`. Always include `置信度：高 / 中 / 低`.
- **Social-media-only evidence is a hard cap** — can never reach
  "强 Alpha 候选".
- **No verified demand → usually "更像主题叙事"**.
- **Third-order theme exposure → usually "更像主题叙事"** unless proven
  otherwise.
- **Shortlist is 3–7 names max.** Entry requires ticker clarity, exact
  bottleneck product, materiality proxy, current market context, non-social
  evidence, catalyst, and disqualifier. Anything missing → `Watchlist / 待核验`.
- **Default output language is Chinese.** Honor this unless the user writes
  in another language.
- **Never give buy/sell/position-size advice.** This skill is research and
  validation, not recommendation.

## Working Conventions

- `SKILL.md` is the single source of truth. Put long-form / niche material
  in `references/` and link from `SKILL.md` — do not duplicate.
- When adding a new reference, update the `## References` section in
  `SKILL.md` so agents can find it.
- When adding a new conclusion state, also update the hard-caps section in
  `SKILL.md` and the "Conclusion Status, Not Letter Rating" guidance.
- Keep `description` (frontmatter) trigger-rich but under one paragraph; it
  is what the host uses for skill activation.

## Local-Only Directories (Never Commit)

These exist on this machine for tool integration but are excluded via
`.gitignore`:

- `.omx/` — OMX harness state, logs, metrics, HUD config.
- `.claude/` — local Claude Code permissions / cache (e.g.
  `settings.local.json`).

If you ever add tooling that writes into another hidden directory, append
it to `.gitignore` rather than committing its contents.

## Common Tasks

- **Add a new reference doc** → drop a `.md` file in
  `references/`, then add a one-line entry under `## References` in
  `SKILL.md`.
- **Tighten the shortlist gate** → edit the "Entry Requirements" and
  "Auto-Exclude" sections of `SKILL.md`; keep them in lockstep so they
  cannot contradict.
- **Add a new domain** (e.g. biotech, defense) → create a new file in
  `references/` and reference it from `SKILL.md`'s "References" section.
  Do not fork the skill — extend it.
- **Run the skill locally** → load `SKILL.md` into a Codex-compatible
  agent and ask a chokepoint question; behavior is spec-driven, there is
  nothing to compile.

## No Commands

There are no build, test, or lint commands. Do not invent a `Makefile`,
`package.json`, or CI workflow unless the user explicitly asks for one —
this repository is documentation + a Markdown skill, nothing more.
