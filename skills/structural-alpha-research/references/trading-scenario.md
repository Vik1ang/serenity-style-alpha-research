# Trading Scenario Layer / 交易推演（非投资建议）

Use this reference when the user asks “怎么交易 / 能不能做 / 买不买 / 卖不卖 / 入场条件 / 观察条件 / 交易推演”. This layer turns a research conclusion into a **scenario plan**, not a trade instruction. It must not output direct buy/sell commands, target prices, stop-loss prices, or position sizing.

## 1. Purpose

交易推演回答的是：在当前证据、价格结构、事件窗口和风险条件下，这个 thesis 处于什么可行动性状态；接下来需要等什么、看什么、什么情况应该放弃。它不是把研究结论直接翻译成“买/卖”。

The layer sits **after** thesis research. Do not run it before cycle proof, demand proof, bottleneck proof, comparative advantage, materiality, market context, and risk checks have been assessed.

## 2. Required Inputs

Before giving a trading scenario, state whether these inputs are verified, stale, missing, or user-provided:

- thesis bucket: Shortlist / Watchlist / Excluded, or A-share thesis-level bucket;
- conclusion status and confidence;
- latest price / market cap / liquidity date, ideally within the last 30 trading days;
- cycle/objectivity evidence: technology route, capex, policy, product pricing, lead time, utilization, or backlog signal;
- comparative-advantage evidence: why the company captures the constrained layer;
- materiality evidence: revenue, segment revenue, contract amount + timing, backlog/order, customer concentration;
- low-base elasticity evidence where relevant: recoverable margin/ROE/profit repair, not structurally poor economics;
- catalyst window: upcoming filing, announcement, earnings, customer validation, policy/cycle event, or industry data;
- invalidation evidence: company denial, weak announcement language, dilution/debt/ST/delisting risk, margin/cash-flow failure;
- market-structure state: normal, crowded, R2/R3 data insufficient, large-cap crowding, small-cap relay, limit-up/limit-down liquidity risk.

If current market data is not available, use **数据不足** or **仅观察**, not “可交易研究对象”.

## 3. Trading Scenario Statuses

Use exactly one status. Do not invent new buckets unless the user explicitly asks for a custom format.

### 可交易研究对象

Use when the thesis is research-valid enough to monitor for execution triggers: demand and bottleneck proof are both satisfied, materiality is verified or strongly cross-derived, key red flags are not dominant, and current market context is available. This is **not** a buy call; it means the name is eligible for a trading plan if the user’s own constraints allow it.

### 等待触发

Use when the thesis is plausible but needs a specific event before actionability improves. Typical missing triggers: earnings confirmation, segment revenue, contract amount + timing, customer order, regulatory reply, price/volume reset, liquidity normalization, or completion of a catalyst window.

### 仅观察

Use when research interest exists but the evidence chain is incomplete. Typical causes: weak demand proof, unclear bottleneck, missing materiality, stale market data, no non-social-media anchor, or unresolved A-share announcement ambiguity. This is the default for early optionality.

### 回避交易

Use when downside risks dominate the scenario. Typical causes: strong company denial, Excluded thesis bucket, severe financial/governance red flags, R3 small-cap relay risk, liquidity trap, valuation/crowding with no remaining misclassification, or thesis invalidation.

### 数据不足

Use when the requested trading scenario depends on unavailable or stale market/financial data. This is stricter than “仅观察”: the issue is not just thesis incompleteness, but inability to assess the current trading setup.

## 4. Status Mapping Rules

These are defaults; explain exceptions explicitly.

- **Shortlist + current market data + no dominant red flags + objective cycle evidence** → 可交易研究对象 or 等待触发.
- **Shortlist + catalyst missing / crowded price / stale liquidity data** → 等待触发.
- **Watchlist / Early Optionality** → 仅观察 or 等待触发, never 可交易研究对象 unless the missing checkpoint is resolved.
- **Excluded thesis** → 回避交易, unless discussing a separate thesis-level bucket for the same company.
- **A-share strong announcement counter-evidence** → 回避交易 for the affected thesis.
- **A-share weak counter-evidence or template cooling** → 仅观察 / 等待触发, depending on materiality and market structure.
- **R3 small-cap relay / limit-up crowding with incomplete evidence** → 回避交易 or 等待触发 after cooling; do not call it 可交易研究对象.
- **No current market context** → 数据不足, or 仅观察 if the user only wants research monitoring.

## 5. Checkpoints That Can Upgrade Status

A trading scenario can only upgrade when a missing gate is resolved. Use concrete checkpoints, not narrative adjectives.

Research checkpoints:

- contract amount + delivery / revenue-recognition timing;
- disclosed segment revenue reaching the materiality threshold;
- customer order, qualification, long-term agreement, or prepayment;
- backlog/order conversion into revenue;
- gross margin / operating margin improvement tied to the bottleneck product;
- capex/capacity progress without destructive dilution.

A-share-specific checkpoints:

- company announcement clarifies that the target thesis is not denied;
- regulatory inquiry reply supports, rather than weakens, the thesis;
- R2/R3 minimum market-structure data package becomes available;
- market cap date is current and size bucket is known;
- media “订单正在交付” is confirmed by contract, customer, or financial disclosure.

Trading-structure checkpoints:

- price/volume behavior cools after a crowded move;
- liquidity is sufficient for observation without gap/limit-board trap;
- implied volatility / turnover / short interest / options crowding, where available, no longer dominates the thesis;
- catalyst window is close enough and evidence quality is high enough to monitor.

## 6. Conditions That Downgrade Or Kill The Scenario

Downgrade to **仅观察 / 回避交易 / 数据不足** when any of these dominate:

- demand proof fails or remains social-media-only;
- bottleneck product is not exact or not company-owned;
- materiality remains below threshold with no contract amount + timing;
- company announcement fully denies, says no scale, or says revenue share is too low for the affected thesis;
- major dilution, refinancing stress, ST/delisting/audit red flag, or severe debt/liquidity risk appears;
- valuation/crowding already reflects the thesis and no misclassification remains;
- R3 relay risk overwhelms fundamentals;
- latest price/market cap/liquidity data is unavailable or stale for a trading judgment.

## 7. Risk-Control Topics To Discuss

Risk-control discussion should identify risks and monitoring rules, not prescribe exact stops or position sizes.

Cover the relevant items:

- gap risk around announcements, earnings, regulatory inquiry replies, or financing;
- A-share limit-up/limit-down liquidity and inability to exit;
- small-cap relay / theme-chase risk;
- large-cap crowding / valuation compression risk;
- dilution, refinancing, pledge, ST/delisting, audit, receivables/inventory, cash-flow risk;
- customer concentration and one-off order risk;
- technology-route substitution;
- evidence staleness and source quality.

Allowed phrasing:

- “风险控制重点是避免在 R3 接力阶段追高，等待公告/成交结构冷却后再评估。”
- “如果出现强公告反证，该 thesis 应转为回避交易。”
- “当前缺少最新流动性和市值数据，不能给可交易状态。”

Disallowed phrasing:

- “买入 / 卖出 / 加仓 / 清仓” as a command;
- exact position size such as “三成仓 / 半仓”;
- target price or stop-loss price;
- personalized allocation based on the user’s portfolio.

## 8. Output Block

Use this block after the research conclusion when trading scenario output is requested:

```markdown
## 交易推演（非投资建议）

- 当前交易状态：可交易研究对象 / 等待触发 / 仅观察 / 回避交易 / 数据不足
- 状态理由：基于哪些已验证证据、缺口、风险或市场结构
- 为什么不是直接买卖建议：缺少哪些个性化约束、实时数据或执行条件
- 进入交易观察的 checkpoints：1–5 个具体数据 / 事件 / 公告 / 市场结构条件
- 不宜交易条件：会导致降级或放弃的反证
- 未来 1–4 周触发器：公告、财报、监管回复、客户/同行验证、成交结构、政策/产业数据
- 风险控制重点：流动性、跳空、涨跌停、估值拥挤、再融资、财务红旗、证据时效
- 边界声明：这是交易情景推演，不是买入、卖出、仓位、目标价或止损价建议。
```

For stock screens, add one concise column or bullet per key name:

```markdown
| 公司/thesis | 研究桶 | 交易推演状态 | 等待什么 | 回避条件 |
|---|---|---|---|---|
```

## 9. Quality Bar

A good trading scenario is falsifiable. It should let the user know exactly what evidence would upgrade, delay, or kill the setup. If the output only says “谨慎关注 / 注意风险” without concrete checkpoints, it is too vague.
