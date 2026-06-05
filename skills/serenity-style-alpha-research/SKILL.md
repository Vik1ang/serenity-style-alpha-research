---
name: serenity-style-alpha-research
description: Use when doing Serenity/@aleabitoreddit-style stock selection or candidate screening from AI/semiconductor supply-chain bottleneck theses, market news, X/Twitter stock ideas, company announcements, earnings clues, or user asks who benefits, which stocks to research, whether a chokepoint alpha logic is valid, or how to verify a small-cap supply-chain stock thesis.
metadata:
  short-description: Serenity-style chokepoint alpha research
---

# Serenity-Style Alpha Research

## Purpose

Analyze market/news/company clues through the Serenity-style “chokepoint” lens: **certain demand → constrained supply → low market attention → value capture → catalyst → anti-thesis**. The goal is stock selection research: build a candidate universe, filter for investable bottleneck exposure, then decide which names deserve deeper due diligence. Do not copy Serenity’s tickers or hype; test whether a small, overlooked company sits at a hard-to-replace bottleneck that can transmit into financials.

Default output language: **Chinese**.

This skill produces stock-research candidates, thesis validation, and verification plans. It does not give buy/sell/position-size advice.

## What “Serenity-Style” Means Here

Use the public Serenity/@aleabitoreddit framing as an inspiration, not an authority. Recent summaries describe the method as focusing on AI/semiconductor supply-chain “choke points”: identify a validated major trend, map the chain, find the hardest-to-replace upstream bottleneck, gather evidence, assess risks, and look for catalysts. Treat all self-published returns, public holdings, and social-media claims as unverified unless independently confirmed.

Core five-factor test:

1. **Certain demand** — real downstream demand is visible or strongly verifiable.
2. **Constrained supply** — the link is hard to expand, qualify, substitute, or replicate.
3. **Low attention** — market still labels the company as old/niche/irrelevant.
4. **Value capture** — bottleneck status can become revenue, margin, operating leverage, or cash flow.
5. **Catalyst** — 1–4 quarter events can force market recognition.


## Stock-Picking Workflow

When the user asks “谁受益 / 有哪些票 / 找类似 Serenity 的机会 / 帮我筛选”, use a **longlist → evidence filter → shortlist → deep dive** flow:

1. **Define universe** — exchange/region if known (US / A-share / HK / Europe / Canada), market-cap range, liquidity constraints, and sector boundary. If unspecified, state assumptions and prefer liquid listed equities with verifiable filings.
2. **Longlist by supply-chain layer** — list companies by exact product layer, not by theme label. Include exchange/ticker and avoid ambiguous names.
3. **Filter for first-order exposure** — prioritize direct bottleneck sellers; downgrade distributors, broad conglomerates, or low-purity exposure.
4. **Investability filter** — current market cap, average liquidity, free float, dilution/SBC/debt, listing risk, governance, and financial-report quality.
5. **Evidence filter** — demand proof, customer/qualification, backlog/orders, segment revenue, gross margin, capex/capacity.
6. **Shortlist** — 3–7 names maximum unless user requests a broad screen. Rank by research priority, not “buy” attractiveness.
7. **Deep dive trigger** — only deep dive names with enough data to test revenue mix, value capture, and anti-thesis.

For each candidate, require at minimum: **ticker/exchange, exact bottleneck product, exposure purity, latest market cap, latest revenue or segment proxy, non-social-media evidence, key catalyst, key disqualifier**. If these cannot be verified, keep it in “Watchlist / 待核验”, not shortlist.


## Shortlist Gate

The shortlist is the core stock-selection output. Do not let a company enter shortlist just because it is thematically related. Every candidate must pass all **Entry Requirements** and avoid all **Auto-Exclude** rules.

A company cannot enter **Shortlist** unless both **Demand Proof** and **Bottleneck Proof** are explicitly satisfied. If either is missing, downgrade to **Watchlist / 待核验**.

### Entry Requirements

A company can enter **shortlist** only when all are available or reasonably verified:

1. **Ticker clarity** — exact ticker, exchange, and company identity are unambiguous.
2. **Bottleneck product** — the exact product/process/resource is named, not just a theme label.
3. **Exposure path** — explain whether it is first-order, second-order, or third-order exposure. First-order is preferred.
4. **Materiality proxy** — latest revenue, segment revenue, customer concentration, backlog/order book, or another proxy showing the bottleneck could matter to total financials.
5. **Current market context** — latest market cap or valuation proxy, plus enough liquidity context to avoid obvious uninvestable names.
6. **Evidence anchor** — at least one non-social-media evidence source: filing, earnings call, company presentation, customer/supplier/competitor evidence, or credible industry data.
7. **Key catalyst** — one plausible 1–4 quarter event that can update market perception.
8. **Key disqualifier** — the most important fact that would remove it from the shortlist.

Market context means price / market cap / liquidity / valuation data from the last 30 trading days. Financial data should use the latest official filing or company update.

Materiality must be based on realized revenue, disclosed segment revenue, signed orders/backlog, customer concentration, or conservative cross-derived data. TAM, assumed market share, and social-media revenue estimates do not qualify. Default threshold: bottleneck revenue ≥10% of TTM revenue, or 12-month disclosed backlog/orders ≥5% of TTM revenue.

### Buckets

Use three buckets, not one blended list:

- **Shortlist** — passes entry requirements; deserves deep dive.
- **Watchlist / 待核验** — interesting but missing materiality, market cap, customer, order, margin, or dilution data.
- **Excluded / 剔除** — fails bottleneck, exposure, investability, or evidence tests.

### Auto-Exclude From Shortlist

Keep the name out of shortlist if any are true:

- only social-media evidence;
- ticker/company identity ambiguous;
- no clear bottleneck product;
- exposure is third-order and financial transmission is not shown;
- no revenue/segment/materiality proxy;
- severe unresolved dilution, debt, going-concern, delisting, or disclosure risk;
- market cap/valuation and liquidity cannot be checked;
- the thesis is already fully consensus and no remaining misclassification is identified.

  "fully consensus" cannot be judged subjectively. Use objective signs: thesis-linked price move, valuation expansion, attention saturation, trading volume spike, options/IV crowding where available. If multiple signs are present and no remaining misclassification is evidenced, downgrade from Shortlist to Watchlist.

Auto-excluded names may still appear in **Watchlist** or **Excluded** with a short reason.

### Watchlist → Shortlist Upgrade Gate

Watchlist names can upgrade to Shortlist only after the missing gate is resolved: demand proof, bottleneck proof, materiality proxy, current market context, or dilution/liquidity risk.

### Shortlist Ranking

Rank by **research priority**, not attractiveness or buy recommendation. Prioritize names where the next data check can materially change conviction: customer confirmation, segment inflection, backlog conversion, margin improvement, capacity expansion, or dilution risk resolution.


## Small-Cap Red Flag Filter

Apply this after the Shortlist Gate for small-cap, microcap, thinly traded, newly public, OTC, highly promotional, or financing-dependent candidates. This filter is a risk override, not a separate bucket system.

Check these red flags:

1. **Dilution / financing machine** — recent equity issuance, ATM/shelf, convertibles, warrants, high SBC, repeated raises.
2. **Liquidity / free-float trap** — low average dollar volume, wide spreads, limited free float, trading halts, market access constraints.
3. **Balance-sheet stress** — near-term debt maturities, refinancing need, negative FCF, covenant pressure, going-concern language.
4. **Customer concentration fragility** — single-customer thesis, anonymous customer, one-off order, customer bargaining power or switching risk.
5. **Disclosure / governance / listing quality** — poor disclosure, promotional management, OTC/delisting risk, weak audit/governance, related-party concerns.

If any red flag is material and unresolved, downgrade from Shortlist to Watchlist or Excluded. A strong chokepoint story does not override financing, liquidity, disclosure, or survivability risk.

## Data Discipline

For specific companies/tickers, **verify latest data before judging** whenever tools are available: latest filings, earnings/transcripts, investor presentations, market cap, revenue, segment mix, backlog/order book, gross margin, capex, dilution/SBC/debt, liquidity, valuation, and recent news.

Evidence hierarchy:

1. **Primary** — filings, earnings calls, company presentations, exchange filings, official announcements.
2. **Cross-check** — customer/supplier/competitor commentary, industry data, technical route evidence.
3. **Market data** — latest price/market cap, liquidity, valuation, short interest/options if relevant.
4. **Secondary** — credible news/sell-side summaries; use as pointers, not final proof.
5. **Social media** — X/Twitter threads and rumors are thesis inputs only; never enough by themselves.

Label key claims as **已验证 / 交叉验证 / 未验证 / 推断** when the distinction matters. If data cannot be verified, write:

> 以下分析基于用户提供的信息和已有框架，关键数据尚未验证。

If key evidence is missing, write:

> 当前缺少关键验证数据，该结论只能作为研究假设，不能作为强 Alpha 结论。

## Response Depth

The user may not always want a full memo. Choose the lightest depth that answers the question:

- **快速 Triage（默认）**：for one news item, one tweet, or “这个逻辑对吗?” Answer with thesis, strongest evidence, weakest link, required verification, and conclusion status.
- **选股 Shortlist**：for “谁受益/有哪些票/找标的/筛选”. Build longlist by supply-chain layer, verify investability/evidence, then return a research-priority shortlist.
- **完整研究 Memo**：for “深度分析/完整拆解/比较几个公司/写研究框架”. Use the full template in `references/output-template.md`.
- **公司核验**：for named tickers. Verify current financial/market data first, then assess exposure and financial transmission.

If uncertain, default to 快速 Triage and say what would be needed for a full memo.

## Mandatory Reasoning Sequence

For every analysis, at least cover these gates:

1. **Narrative** — what is the surface story and obvious beneficiary?
2. **Demand proof** — is there real demand, not just narrative?
3. **Chain map** — where does the company/product sit in the supply chain?
4. **Bottleneck proof** — why is this link hard to replace/expand/qualify?
5. **Company exposure** — product, customer, revenue mix, first/second/third-order exposure.
6. **Financial transmission** — revenue, margin, operating leverage, cash flow, balance sheet, dilution.
7. **Market neglect** — old label vs possible new label; why mispriced?
8. **Catalyst** — what can force recognition within 1–4 quarters?
9. **Anti-thesis** — what would kill the thesis?
10. **Conclusion status** — textual conclusion, not A/B/C/D. For stock screens, output research priority and disqualifiers, not buy/sell calls.

## Conclusion Status, Not Letter Rating

Do **not** use A/B/C/D ratings. Use one of these conclusion states with confidence:

- **强 Alpha 候选（需持续验证）** — demand, bottleneck, exposure, value capture, catalyst, and risk data are mostly verified.
- **有潜力，但关键数据待验证** — logic is plausible, but one or more critical links are missing.
- **更像主题叙事** — demand/exposure/financial transmission is weak or indirect.
- **暂时否定 / 回避研究** — pseudo-bottleneck, no material exposure, financial/risk profile poor, or evidence contradicts the thesis.

Always include **置信度：高 / 中 / 低** and the reason. Do not let a strong story override missing evidence.

Hard caps:

- Only X/Twitter/social-media evidence → cannot be “强 Alpha 候选”.
- No verified demand → usually “更像主题叙事”.
- No revenue mix/company exposure data → at most “有潜力，但关键数据待验证”.
- Third-order theme exposure → usually “更像主题叙事”.
- Severe dilution/debt/liquidity risk unresolved → cannot be “强 Alpha 候选”.

## What To Remove From Scope

This skill is for listed-equity stock selection and company/industry supply-chain alpha research, especially AI/semiconductor/optical/datacenter-power chokepoints. Do not use it for broad macro, pure technical trading, CTD/basis/ETF dislocation, CTA, or generic market-structure analysis unless the user explicitly asks to adapt the framework.

## References

- Use `references/output-template.md` for full research memo structure.
- Use `references/domain-extensions.md` for AI infrastructure, semiconductor, datacenter power, crypto-mining-to-HPC, and A/H/HK/US supply-chain variants.
- Use `references/scoring.md` only for numerical elasticity math or factor checklists; do not output A/B/C/D ratings.
- For A-share research, start with `references/a-share-skill-spec-FINAL.md`; load `references/a-share-skill-spec-draft.md`, R4/R5/R6 detail files, and R1 source/review files only as needed.
- A-share detailed references:
  - `references/a-share-4-pillars-spec.md` — R1 source spec and session record for the four A-share reconstruction pillars.
  - `references/a-share-4-pillars-spec-hermes-review.md` — Hermes R1 review only; does not cover R4-R6 updates.
  - `references/a-share-4-pillars-peer-discussion-r1.md` — R1 peer-discussion and three hardening rules.
  - `references/a-share-skill-spec-draft.md` — D3 working draft and R4-R6 index.
  - `references/a-share-r4-thesis-bucketing-announcement-calibration.md` — thesis-level bucketing, announcement counter-evidence, and media-order confirmation rule.
  - `references/a-share-r5-ma-target-layering-smallcap-redflags.md` — M&A/new-vehicle layering and company-level financial/governance red flags.
  - `references/a-share-r6-market-structure-minimum-evidence.md` — R2/R3 market-structure evidence, market-cap date, and large-cap vs small-cap risk pricing.
