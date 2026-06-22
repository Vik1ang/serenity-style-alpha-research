---
name: structural-alpha-research
description: Use when doing structural alpha research that combines supply-chain bottleneck stock selection with a global tech-cycle, objective-evidence, liquidity, and low-ROE elasticity overlay; candidate screening from AI, semiconductor, datacenter-power, China A-share, or other bottleneck theses; market news; social-media ideas; company announcements; earnings clues; thesis validation; or non-advisory trading scenarios.
metadata:
  short-description: Structural alpha research
---

# Structural Alpha Research

## Purpose

Analyze listed equities through **cycle change / technology inflation → certain demand → constrained supply → comparative advantage → low attention → value capture / low-base elasticity → catalyst → anti-thesis**. Treat public structural alpha framing and global-cycle / objectivity method summaries as inspiration, not authority; do not copy tickers, holdings, quotes, or hype. Default output language: **Chinese**.

This skill may produce **交易推演（非投资建议）**, but not direct buy/sell/position-size/target/stop instructions.

## 硬约束（R-12~16）

- **R-12 — 不输出直接交易指令：** only scenarios, triggers, invalidation, and risk controls.
- **R-13 — 不照抄重型多-skill 架构：** keep one research entry until lifecycle tooling is proven.
- **R-14 — 不削弱现有证据链：** new modules may refine, never replace, thesis bucketing, counter-evidence, or company-level red flags.
- **R-15 — 防止 reference 漂移：** every runtime reference needs a valid index entry and clear owner.
- **R-16 — Registry 先于自动化：** no cron or continuous alerts before Registry, citation, and data-status contracts are proven.

## Core Model

1. **Cycle / technology inflation** — a global technology, capex, policy, or physical-supply cycle is changing objective demand, pricing, lead time, or profit pools.
2. **Certain demand** — downstream demand is visible and verifiable.
3. **Constrained supply** — expansion, qualification, substitution, or replication is difficult.
4. **Comparative advantage** — the target company or region has a credible advantage in the constrained layer.
5. **Low attention** — the market still uses an old or incomplete label.
6. **Value capture / low-base elasticity** — the bottleneck can transmit into revenue, margin, cash flow, operating leverage, or ROE/profitability repair from a depressed base.
7. **Catalyst** — a 1–4 quarter event can force recognition.
8. **Anti-thesis / objective exit** — define what data would prove the thesis wrong.

## Stock-Picking Workflow

For “谁受益 / 找标的 / 帮我筛选”, run **universe → chain longlist → first-order exposure → investability → evidence → shortlist → deep dive**. State assumptions when region, size, or liquidity is unspecified; return 3–7 Shortlist names unless the user requests a broad screen.

Each candidate needs: ticker/exchange, exact bottleneck product, exposure order/purity, cycle driver, comparative-advantage reason, latest market cap and liquidity, latest revenue/segment proxy, customer concentration / platform-transition risk where relevant, low-base/ROE/profitability elasticity, backlog/unit-economics quality where relevant, non-social evidence, catalyst, and disqualifier. Missing critical fields means **Watchlist / 待核验**, not Shortlist.

**A 股 specific routing:** use R4/R5/R6 as the base. Load R9 for Biotech BD income quality. Load R10 only when a large-cap core thesis already passes the base gates and needs residual re-rating/price-in analysis.

**Cycle/objectivity overlay:** load `references/cycle-objectivity-overlay.md` when the user asks to combine structural alpha with global-cycle / objectivity methods, when a thesis depends on global tech cycles / ROE repair / liquidity / objectivity, or when optimizing a stock-selection output beyond the base chokepoint gates.

## Validation Protocol

When changing the skill itself, or when the user asks whether the framework “works”, validate with a mixed basket rather than only attractive names:

1. At least two likely positives.
2. At least two high-quality but crowded/price-in boundary cases.
3. At least two exposure-impure, customer-concentrated, or platform-transition cases.
4. At least two red-flag false positives where revenue, backlog, policy support, or social attention could mislead the framework.

Record validation samples and conclusions under `docs/decisions/`, not runtime references. Do not let historical validation tickers become built-in recommendations.

For A-share validation, the basket must additionally cover thesis-level splitting, R2/R3 market structure, second-order exposure, order/backlog quality, company-level red flags, and small-cap/liquidity cases.

## Shortlist Gate

A company cannot enter **Shortlist** unless **Cycle Proof**, **Demand Proof**, **Bottleneck Proof**, and **Comparative-Advantage Proof** are explicit, all entry requirements are reasonably verified, and no overriding exclusion applies.

### Entry Requirements

1. Exact ticker, exchange, and identity.
2. Exact bottleneck product/process/resource.
3. First/second/third-order **exposure path**; prefer first-order.
4. Objective cycle evidence: price/lead-time change, capex, orders, utilization, policy-driven demand, or technology-route shift.
5. Comparative advantage or qualification reason: customer lock-in, process, channel, global share, certification, geography, cost, or engineering advantage.
6. Realized revenue, segment revenue, signed orders/backlog, customer concentration, architecture/platform-transition exposure, or conservative cross-derived **materiality proxy**.
7. Price, market cap, liquidity, and valuation from the **last 30 trading days**; financials from the latest official filing/update.
8. Low-base elasticity check where relevant: ROE/profit margin depressed by cycle/R&D/capacity, not permanently low-quality economics; backlog growth must pass gross-margin, cash-conversion, working-capital, cancellation, and financing-dependency checks.
9. At least one non-social **evidence anchor**.
10. One plausible 1–4 quarter catalyst.
11. One decisive disqualifier.

TAM, assumed market share, and social-media revenue estimates do not qualify. Default threshold: bottleneck revenue **≥10% of TTM revenue**, or disclosed 12-month backlog/orders **≥5% of TTM revenue**.

### Buckets

- **Shortlist** — all gates pass; deserves deep research.
- **Watchlist / 待核验** — thesis is plausible but a required gate or risk check is unresolved.
- **Excluded / 剔除** — bottleneck, exposure, investability, evidence, or risk tests fail.

### Auto-Exclude / Downgrade

Keep out of Shortlist when identity/product is unclear; evidence is social-only; exposure is third-order without financial transmission; materiality or current market context is unavailable; or dilution, debt, going-concern, delisting, disclosure, governance, or liquidity risk is severe.

“Fully consensus” requires objective signs such as thesis-linked price move, **valuation expansion**, attention saturation, volume spike, or options/IV crowding. Multiple signs plus no remaining misclassification → Watchlist, not an automatic narrative judgment.

Hard caps:

- **Price-in / crowding cap:** good company + good industry + strong earnings is not enough. When valuation expansion, news saturation, market-cap scale, and thesis-linked price action are all high, default to Watchlist / deep-dive only unless a concrete remaining misclassification is proven.
- **Customer concentration / platform-transition cap:** for AI, semiconductor, optics, datacenter power, and other platform-linked chains, unresolved single-customer dependence, route transition risk, insourcing, dual-sourcing, or customer qualification uncertainty caps the thesis below strong Alpha.
- **Backlog / unit-economics cap:** revenue growth, orders, backlog, policy loans, or offtake are insufficient when gross margin path, cash conversion, funding need, cancellation risk, or dilution risk is unresolved.
- **Catalyst-horizon cap:** a structurally correct thesis with no plausible 1–4 quarter recognition event remains Watchlist, not Shortlist.

### Watchlist → Shortlist Upgrade Gate

Upgrade only after the missing cycle, demand, bottleneck, comparative-advantage, materiality, market-context, dilution, or liquidity gate is resolved. Rank names by research priority and information value, not buy attractiveness.

## Small-Cap Red Flag Filter

For small-cap, microcap, thinly traded, newly public, OTC, promotional, or financing-dependent names, check:

1. **Dilution / financing machine**
2. **Liquidity / free-float trap**
3. **Balance-sheet stress**
4. **Customer concentration fragility**
5. **Disclosure / governance / listing quality**

Any material unresolved red flag overrides the story and downgrades to Watchlist or Excluded.

## Data Discipline

Verify current filings, announcements, presentations, market cap, segment mix, backlog, margins, capex, dilution/SBC/debt, liquidity, valuation, and recent news whenever tools exist.

Evidence hierarchy: **Primary** filings/official announcements → **Cross-check** customers/suppliers/competitors/industry → **Market data** (price, volume, liquidity, valuation, lead time, product pricing) → **Secondary** media/sell-side pointers → **Social media** thesis input only.

Label decisive claims **已验证 / 交叉验证 / 未验证 / 推断**. Separate **原始证据** from **按框架推演**. If verification is unavailable, state that the analysis relies on supplied information; missing key evidence means a research hypothesis, not a strong Alpha conclusion.

> 以下分析基于用户提供的信息和已有框架，关键数据尚未验证。
>
> 当前缺少关键验证数据，该结论只能作为研究假设，不能作为强 Alpha 结论。

## Response Modes and Mandatory Sequence

Use the lightest mode: quick triage; shortlist; named-company verification; or full memo via `references/output-template.md`.

Every analysis covers: **Narrative** → **Cycle / technology inflation proof** → **Demand proof** → **Chain map** → **Bottleneck proof** → **Comparative advantage** → **Company exposure** → **Financial transmission / low-base elasticity** → **Market neglect** → **Catalyst** → **Anti-thesis / objective exit** → textual conclusion. Do not substitute price appreciation for thesis validation.

## Trading Scenario Layer / 交易推演（非投资建议）

When asked “怎么交易 / 买不买 / 能不能做”, output:

- **可交易研究对象**
- **等待触发**
- **仅观察**
- **回避交易**
- **数据不足**

Include current state, why it is not a direct recommendation, checkpoints, no-trade conditions, 1–4 week triggers, and risk-control focus. Reframe requests for commands into scenarios. Load `references/trading-scenario.md` for detailed mappings.

## Conclusion Status, Not Letter Rating

Do **not** use A/B/C/D ratings. Include confidence (高/中/低) and choose:

- **强 Alpha 候选（需持续验证）**
- **有潜力，但关键数据待验证**
- **更像主题叙事**
- **暂时否定 / 回避研究**

Social-only evidence, no verified cycle/demand, no bottleneck, missing comparative advantage, missing exposure/materiality, third-order transmission, or unresolved severe financing/liquidity risk caps the conclusion below strong Alpha.

## Scope and Runtime References

Scope: listed-equity stock selection and company/industry chokepoint research. Exclude broad macro, pure technical trading, basis/CTA, and generic market-structure analysis unless explicitly adapted.

- General: `references/output-template.md`, `references/trading-scenario.md`, `references/domain-extensions.md`, `references/scoring.md`, `references/cycle-objectivity-overlay.md`.
- A-share entry: `references/a-share-skill-spec-FINAL.md`.
- A-share base: `references/a-share-r4-thesis-bucketing-announcement-calibration.md`, `references/a-share-r5-ma-target-layering-smallcap-redflags.md`, `references/a-share-r6-market-structure-minimum-evidence.md`.
- A-share specialist: `references/a-share-r9-biotech-bd-quality.md`, `references/a-share-r10-large-cap-rerating-residual.md`.
- Provenance/examples only when needed: `references/a-share-4-pillars-spec.md`, its R1 review/peer-discussion files, `references/a-share-skill-spec-draft.md`, and `references/a-share-worked-examples.md`.
