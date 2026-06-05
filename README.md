# Serenity-Style Alpha Research

A Codex/OpenAI skill package for listed-equity alpha research through a
Serenity-style chokepoint lens: **certain demand → constrained supply → low
attention → value capture → catalyst → anti-thesis**. Default output language is
Chinese.

This repository is a **skill package**, not a runnable application. The shipping
artifact is the skill at `.codex/skills/serenity-style-alpha-research/`, which is
loaded by Codex-compatible agents at runtime.

## Repository Layout

```
.
├── .codex/
│   └── skills/
│       └── serenity-style-alpha-research/
│           ├── SKILL.md                 # skill entry point + trigger metadata
│           ├── references/
│           │   ├── output-template.md   # full memo + shortlist format
│           │   ├── domain-extensions.md # AI / semi / DC-power variants
│           │   ├── scoring.md           # elasticity math & factor checklist
│           │   ├── a-share-skill-spec-FINAL.md
│           │   ├── a-share-skill-spec-draft.md
│           │   ├── a-share-4-pillars-*.md
│           │   ├── a-share-r4-*.md
│           │   ├── a-share-r5-*.md
│           │   └── a-share-r6-*.md
│           └── agents/
│               └── openai.yaml          # UI-facing skill metadata
├── README.md
├── CLAUDE.md
└── .gitignore
```

`.omx/` and `.claude/` are local agent-harness state and are intentionally
excluded from version control.

## Install / Use

Copy the skill directory into any Codex-compatible environment:

```bash
# project-level install
cp -r .codex/skills/serenity-style-alpha-research \
      <your-project>/.codex/skills/

# or user-level install
cp -r .codex/skills/serenity-style-alpha-research \
      ~/.codex/skills/
```

The skill is triggered by phrases like “谁受益 / 找类似 Serenity 的机会 / 帮我筛选
/ 这个逻辑对吗 / 验证一个 chokepoint thesis”.

## What It Produces

- **快速 Triage** — for one news item, tweet, announcement, or “does this logic
  hold?”.
- **选股 Shortlist** — longlist → evidence filter → shortlist/watchlist/excluded.
- **完整研究 Memo** — use `references/output-template.md` for deep dives.
- **公司核验** — verify current market and financial data before judging exposure.
- **A 股 thesis-level 分桶** — for A-share names, start from
  `references/a-share-skill-spec-FINAL.md`, then load D3/R4/R5/R6 detail files as
  needed.

Conclusion is always textual status with confidence — never A/B/C/D ratings and
never buy/sell/position-size advice.

## A-share Research Stack

A-share support is a separate methodology stack, not a direct translation of the
US chokepoint workflow.

Read order:

1. `references/a-share-skill-spec-FINAL.md` — final one-page map and file index.
2. `references/a-share-skill-spec-draft.md` — D3 working draft and R4-R6 index.
3. `references/a-share-r4-thesis-bucketing-announcement-calibration.md` —
   thesis-level bucketing, announcement counter-evidence, media-order rule.
4. `references/a-share-r5-ma-target-layering-smallcap-redflags.md` — M&A/new
   vehicle layering and company-level financial/governance red flags.
5. `references/a-share-r6-market-structure-minimum-evidence.md` — R2/R3 market
   structure evidence, market-cap date, and large-cap vs small-cap risk pricing.
6. R1 source/review files (`a-share-4-pillars-*.md`) are provenance and design
   history; load only when reviewing the methodology.

The A-share framework was pressure-tested on three cases: 春秋电子, 鹏鼎控股, and
黄河旋风.

## Data Discipline

Evidence hierarchy, in descending order of weight:

1. Primary — filings, exchange filings, company announcements, earnings calls.
2. Cross-check — customer / supplier / competitor commentary, industry data.
3. Market data — price, market cap, liquidity, valuation, short interest/options.
4. Secondary — credible news / sell-side summaries; pointers, not proof.
5. Social media — thesis input only; never sufficient on its own.

For specific companies, verify latest financial and market data when tools are
available. If key evidence is missing, keep the name in Watchlist / 待核验 or
Excluded; do not force a strong alpha conclusion.

## Editing The Skill

- `SKILL.md` is the entry point and activation surface. Keep frontmatter intact.
- Put long-form methodology in `references/` and link it from `SKILL.md`.
- For A-share edits, update `a-share-skill-spec-FINAL.md` if the change affects
  the top-level read path; update D3/R4/R5/R6 only in their owned scopes.
- Do not invent new conclusion categories. Reuse textual conclusion states and
  confidence levels.


## Known Follow-ups

A-share maintenance items are tracked in `docs/a-share-maintenance-backlog.md`.
Current non-blocking follow-ups include an A-share output template, announcement
counter-evidence sample library, optional R5 filename cleanup, and optional split
of the large R1 provenance file.

## License

No license file is currently shipped. Add one before public distribution.
