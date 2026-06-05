# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

## What This Repo Is

This is a **Codex / OpenAI skill package**, not a runnable application. There is
no `package.json`, no build step, and no test suite. The shipped artifact is the
canonical skill at `skills/serenity-style-alpha-research/` plus its `references/`
directory. The `.codex/skills/serenity-style-alpha-research/` copy is the local
Codex project-level install mirror. Agents load `SKILL.md` at runtime and
selectively load reference docs.

Subject domain: Serenity-style chokepoint alpha stock research — supply-chain
bottlenecks in AI / semiconductor / datacenter-power chains, plus a dedicated
A-share thesis-level methodology stack.

## Key Files

- `skills/serenity-style-alpha-research/SKILL.md` — canonical skill entry point.
- `.codex/skills/serenity-style-alpha-research/SKILL.md` — Codex install mirror; keep synchronized with `skills/`.
  Contains YAML frontmatter (`name`, `description`, `metadata.short-description`)
  and behavioral rules. **Do not strip frontmatter**.
- `skills/serenity-style-alpha-research/agents/openai.yaml` — UI-facing metadata.
- `skills/serenity-style-alpha-research/references/output-template.md` — full research memo and shortlist format.
- `skills/serenity-style-alpha-research/references/domain-extensions.md` — AI / semiconductor / datacenter-power / crypto-mining-to-HPC / A·H·HK·US variants.
- `skills/serenity-style-alpha-research/references/scoring.md` — elasticity math and factor checklist. Do not use it to output A/B/C/D ratings.

## A-share Reference Stack

For A-share work, start with:

- `references/a-share-skill-spec-FINAL.md` — final top-level map and read path.
- `references/a-share-skill-spec-draft.md` — D3 working draft and R4-R6 index.
- `references/a-share-r4-thesis-bucketing-announcement-calibration.md` —
  thesis-level bucketing, 6-level announcement counter-evidence, and media-order
  confirmation rule.
- `references/a-share-r5-ma-target-layering-smallcap-redflags.md` — M&A/new
  business vehicle layering and company-level financial/governance red flags.
- `references/a-share-r6-market-structure-minimum-evidence.md` — R2/R3 market
  structure evidence, required market-cap date, and large-cap vs small-cap risk pricing.

R1 provenance files:

- `references/a-share-4-pillars-spec.md` — original 4-pillar source spec and session log.
- `references/a-share-4-pillars-spec-hermes-review.md` — Hermes review of R1 only;
  it does not cover R4-R6 updates.
- `references/a-share-4-pillars-peer-discussion-r1.md` — R1 peer-discussion and
  three hardening rules.

## Hard Rules To Preserve

- **No A/B/C/D ratings.** Use textual conclusion states with `置信度：高 / 中 / 低`.
- **No direct buy/sell/position-size/target/stop advice.** This is research and validation only; a non-advisory trading scenario layer is allowed only for statuses, checkpoints, triggers, invalidation, and risk controls.
- **Social-media-only evidence cannot support a strong alpha conclusion.**
- **No verified demand usually means “更像主题叙事”.**
- **Third-order theme exposure usually means “更像主题叙事” unless financial
  transmission is proven.**
- **Shortlist requires evidence.** Missing demand proof, bottleneck proof,
  materiality, market context, or risk checks → Watchlist / 待核验 or Excluded.
- **Trading scenario layer is not trade advice.** If users ask “怎么交易 / 买不买 / 卖不卖”, reframe into 可交易研究对象 / 等待触发 / 仅观察 / 回避交易 / 数据不足 plus evidence checkpoints and risks.
- **Default output language is Chinese** unless the user asks otherwise.

## Editing Conventions

- `skills/serenity-style-alpha-research/SKILL.md` is the canonical activation surface; references hold long-form methodology.
- Keep `skills/serenity-style-alpha-research/` and `.codex/skills/serenity-style-alpha-research/` synchronized. The former is for repository readers/distribution; the latter is for local Codex loading.
- When adding a reference doc, add a one-line entry under `SKILL.md` → `## References`.
- When changing A-share methodology, update the owning file:
  - D3 for the overview/index.
  - R4 for thesis-level bucket and announcement evidence.
  - R5 for business-vehicle layering and company-level financial/governance red flags.
  - R6 for market-structure evidence and R2/R3 risk pricing.
  - D4 FINAL if the top-level read path changes.
- Keep root docs (`README.md`, `CLAUDE.md`) aligned with the reference stack.

## Local-Only Directories (Never Commit)

These are excluded via `.gitignore`:

- `.omx/` — OMX harness state, logs, metrics, HUD config.
- `.claude/` — local Claude Code permissions/cache.

If tooling writes into another hidden local directory, add it to `.gitignore`
instead of committing its contents.


## Maintenance Backlog

Known A-share follow-ups live in `docs/a-share-maintenance-backlog.md`. Before
making broad methodology changes, check that file first. In particular, do not
rename the R5 file or split the large R1 provenance file without updating all
references.

## No Commands

There are no build, test, or lint commands. Do not add a `package.json`,
`Makefile`, or CI workflow unless explicitly requested. Verification is file
structure, frontmatter, link/reference consistency, and git diff review.
