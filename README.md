# Serenity-Style Alpha Research

A Codex/OpenAI skill that screens listed equities through the Serenity-style
"chokepoint" lens: **certain demand → constrained supply → low attention →
value capture → catalyst → anti-thesis**. Default output language is Chinese.

This repository is a **skill package**, not a runnable application. The
shipping artifact is the skill definition at
`.codex/skills/serenity-style-alpha-research/`, which is loaded by Codex /
compatible agents at runtime.

## Repository Layout

```
.
├── .codex/
│   └── skills/
│       └── serenity-style-alpha-research/
│           ├── SKILL.md                 # entry point, mandatory frontmatter
│           ├── references/
│           │   ├── output-template.md   # full memo + shortlist format
│           │   ├── domain-extensions.md # AI / semi / DC-power variants
│           │   ├── scoring.md           # elasticity math & factor checklist
│           │   └── a-share-skill-spec-draft.md
│           └── agents/
│               └── openai.yaml          # agent descriptor
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

The skill is triggered by phrases like "谁受益 / 找类似 Serenity 的机会 / 帮我筛选
/ 这个逻辑对吗 / 验证一个 chokepoint thesis".

## What It Produces

- **快速 Triage** — for a single news item / tweet / "does this logic hold?".
- **选股 Shortlist** — for "who benefits / which tickers / screen candidates".
  Longlist → evidence filter → shortlist (3–7 names, max) → watchlist / excluded.
- **完整研究 Memo** — for deep dives. Uses `references/output-template.md`.
- **公司核验** — for named tickers. Verify current market & financial data
  first, then assess exposure and financial transmission.

Conclusion is always **textual status** (强 Alpha 候选 / 有潜力但待验证 /
更像主题叙事 / 暂时否定) with confidence (高/中/低) — **never** A/B/C/D
ratings, and **never** buy/sell calls.

## Data Discipline

Evidence hierarchy, in descending order of weight:

1. Primary — filings, earnings calls, company presentations, exchange filings.
2. Cross-check — customer / supplier / competitor commentary, industry data.
3. Market data — price, market cap, liquidity, valuation, short interest.
4. Secondary — credible news / sell-side summaries (pointers, not proof).
5. Social media — thesis input only; never sufficient on its own.

Any key claim can be labelled **已验证 / 交叉验证 / 未验证 / 推断** when the
distinction matters. Hard caps apply: a social-media-only thesis can never
reach "强 Alpha 候选".

## Editing The Skill

- `SKILL.md` is the source of truth for frontmatter (`name`, `description`,
  `metadata.short-description`) and behavioral rules. Keep it self-contained —
  agents load it as a single document.
- Put long-form / niche material in `references/` and link from `SKILL.md`.
- Do not invent new conclusion categories. Reuse the four textual states and
  the three confidence levels.

## License

No license file is currently shipped. Add one before public distribution.
