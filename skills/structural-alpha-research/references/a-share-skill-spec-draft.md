# A 股 Structural Alpha Skill Spec Draft

## 1. 概要

本草稿是 c 路径 3 步的压缩入口：R1 形成 A 股方法论骨架，R2 用已知案例倒推补漏洞，R3 用春秋电子做一次真实研究校验。完整底稿见 `references/a-share-4-pillars-spec.md`；本文件只保留可转成 A 股 skill 的主路径、分桶、执行顺序、worked example 和 R4-R6 已展开，避免继续沿用美股 gate 逐条翻译。

## 2. 4 件 spec

> 引用来源：`references/a-share-4-pillars-spec.md`。本节只保留每件的用途、迁移边界和执行摘要；完整判断规则以原 4 件 spec 为准。

### 2.1 政策 / 周期前置（Policy / Cycle Front-Loading）

A 股研究不能直接从“全球大需求”开始拆产业链，必须先判断这条链是否处在政策允许、资金支持、产业周期配合、库存/价格/订单方向一致的窗口。政策在这里不是完整 demand proof，而是 demand eligibility / background condition：它让某条链有资格产生需求，但不证明需求已经发生。

执行上先看三类证据：政策是否点到具体链条并有资金、试点、招标或时间表；产业周期是否有价格、库存、交期、capex、订单或上下游公告交叉验证；公司是否有可追踪入口，包括产品、客户、订单、收入、合同、产能、募投或并表。核心补丁是：背景通过 ≠ 公司受益，公司入口必须单独验证。

### 2.2 倒序信息传播（Inverted Information Diffusion）

美股常见路径是卖方/机构覆盖逐步推动价格发现；A 股经常反过来：政策文件、媒体标题、雪球/股吧、短线复盘、涨停板、龙虎榜、异动公告先行，卖方研报和机构确认反而滞后。因此“卖方覆盖少”不能直接等同“低关注”。

执行上要先判断传播阶段：Stage 0 是未扩散；Stage 1 是政策/产业线索刚出现；Stage 2 是雪球、股吧、同花顺热榜、短线复盘开始集中；Stage 3 是涨停、龙虎榜、异动公告和公司澄清共同出现。传播阶段只用于判断 attention / crowding / price-in，不构成 demand proof。

### 2.3 重估触发路径（Re-rating Trigger Path）

A 股重估不是单线条“业绩验证 → 机构覆盖 → re-rating”。更稳的结构是 background + catalyst + confirmation：政策/周期给背景，订单、并购、产能、价格、客户、业绩预告给催化，收入、segment、合同金额、backlog、毛利率、现金流和并表数据给确认。

执行上要区分“可能发生变化”和“已经进入报表”。没有 confirmation 的 catalyst 只能进 Watchlist；没有收入占比 ≥10% 或具体合同金额+时间的 confirmation，不能进 Shortlist。收购类尤其要单独验证标的收入、是否并表、目标客户、合同金额+时间、中国市场适配、对价和商誉，不能把“收购完成”当 demand proof。

### 2.4 涨跌停风险定价（Limit-up / Limit-down Risk Pricing）

A 股涨跌停制度让价格发现不连续，连板、开板剧震、龙虎榜接力、异动公告和监管问询会形成美股 skill 没有的风险定价回路。它不证明基本面真假，但会改变可研究性和分桶优先级。

执行上分 R0-R3：R0 正常定价；R1 题材预热；R2 拥挤定价；R3 高风险接力/退潮风险。若价格已 R3，风险定价优先于 R0 政策背景；若公司公告主动否认核心 thesis，公告反证优先于题材传播。缺龙虎榜、连板、异动公告等完整数据时，不硬判 R3，标 R2 / 数据不足。

## 3. 3 条硬化规则

### Rule 1：冲突优先级规则

当 4 件 spec 给出冲突信号时，按风险优先而不是故事优先处理：R3 涨跌停风险定价 > R0 政策/传播乐观信号；公司强反证 > 题材传播；Materiality 缺失 > catalyst 信号。含义不是政策背景失效，而是该股票不能因背景好直接进入 Shortlist。

### Rule 2：具体 fallback checkpoint

所有“等待落地”必须落到可执行 checkpoint，不接受“等政策细则”“看后续发展”这种空泛 fallback。合格 checkpoint 包括：试点城市公布、招标公告、中标公告、合同签署、订单公告、客户认证、财务并表、财报披露、segment revenue 或明确收入确认窗口。

### Rule 3：Materiality 硬门槛

Materiality 不是 cover 所有缺口的万能补丁，不能弥补政策/周期不成立或公司公告强反证。它是进入 Shortlist 的最终财务硬 gate：没有收入占比 ≥10% 或具体合同金额+时间的 confirmation，一律不进入 Shortlist；只能进入 Watchlist 或 Excluded。

## 4. 5 个失真点补丁

### Patch 1：公告反证 6 级分级

公司公告反证不能只看“澄清”两个字，必须拆成 6 级：完全否认、当前无规模化、占比低、存在不确定性、尚未产生收入、业务正常。强反证 = 完全否认 / 当前无规模化 / 占比低，触发 Excluded；弱反证 = 存在不确定性 / 尚未产生收入，降级 Watchlist；模板降温 = 业务正常，不构成反证，但加 R2 风险标签。

### Patch 2：收购 / 并表专门规则

收购完成 ≠ 业务入口 ≠ demand proof。收购类 thesis 必须单独验证：标的收入、是否并表、目标赛道客户、合同金额+时间、中国市场适配、收购对价、商誉和债务压力。缺任一关键项，标记为 Watchlist — Early Optionality，不进入 Shortlist。

### Patch 3：政策 / 周期到公司入口单独验证

政策/周期通过只说明行业背景允许，不能自动推出公司受益。公司入口必须落到产品、订单、收入、合同、客户、产能、并表或其他可追踪数据；如果只有政策关键词和市场联想，按 anti-hype 处理。

### Patch 4：涨跌停缺数据时不硬判 R3

若缺少完整龙虎榜、连板高度、异动公告、监管问询或成交换手数据，不硬判 R3。默认标记为 R2 / 数据不足，并说明缺哪类市场结构数据。只有在连板、公告反证、异动公告、高位放量等非龙虎榜证据已足够时，才可不依赖龙虎榜直接判 R3。

### Patch 5：Watchlist — Early Optionality 子标签

保留三桶，不新增第四桶。Early Optionality 作为 Watchlist 子标签使用，格式为：`Watchlist — Early Optionality / [缺什么 checkpoint]`。升级条件只能是合同金额+时间、并表收入、客户订单、或收入占比达到硬门槛。

## 5. 三桶分桶规则

默认按 thesis-level 分桶，公司级只做 summary。

公司级 (而非仅小票) 红旗 (ST/退市/质押/商誉/再融资/应收存货/业绩预亏) 可覆盖全部 thesis。

### Shortlist

确认型基本面候选。必须已经越过背景、传播、重估和风险定价的主要冲突；不能只是政策受益、题材扩散或潜在业务入口。

### Watchlist — Early Optionality

早期可选性待核验。适用于存在业务入口或催化、但 confirmation 尚未闭合的 thesis；不能被包装成已确认 alpha。

### Excluded

反证或风险压倒。适用于核心 thesis 被公告否认、传播明显强于财务验证、或价格/财务/治理风险已经主导判断的情况。

## 6. 跑票流程：政策→倒序→重估→涨跌停 + 触发顺序

第一步，跑政策/周期前置。先判断产业背景是否允许需求发生，再单独检查公司是否有可追踪入口；背景不通过时，后续只解释情绪。

第二步，跑倒序信息传播。定位叙事处于早期线索、扩散升温还是拥挤阶段；传播越靠后，越要提高 anti-hype 和 price-in 权重。

第三步，跑重估触发路径。拆 background、catalyst、confirmation 是否闭合；若只有催化没有确认，保留 Watchlist，不进入 Shortlist。

第四步，跑涨跌停风险定价。识别 R0-R3，处理连板、异动公告、龙虎榜和澄清公告；若 R3 与乐观信号冲突，风险优先降级。执行层数据标准 (R2/R3 最低数据包/缺数据处理) 见 a-share-r6-market-structure-minimum-evidence.md。

最终按冲突优先级出结论：风险优先、公告反证优先、财务硬门槛兜底。

## 7. 春秋电子真研究 worked example

### 7.1 公开信息

春秋电子被市场放入 AI PC / 数据中心液冷 / 机器人叙事，短期出现连续涨停和异动公告。公司公开澄清：不生产 AIPC 终端，也不生产 AIPC 芯片或核心部件；无规模化机器人业务或量产机器人产品；已完成 Asetek 收购，但 Asetek 现有主业偏高性能桌面 PC 液冷，数据中心液冷业务此前暂停，未来重启和推广存在不确定性。财报层面，现有公开信息能验证公司主营改善，但不能验证 AI PC、机器人或数据中心液冷已形成 materiality。

### 7.2 4 件结果

政策/周期前置：R1。AI PC、液冷、机器人均有产业背景，但公司入口分化明显。

倒序信息传播：R3。题材先于财务验证扩散，出现连续涨停、热榜、市场传闻和公司澄清。

重估触发路径：R1/R2。Asetek 收购是潜在 catalyst，但 confirmation 未闭合；AI PC 和机器人 thesis 因公告反证退出。

涨跌停风险定价：R3。连续涨停、异动公告、风险提示和核心概念澄清叠加。

### 7.3 分桶

AI PC thesis：Excluded。

机器人 thesis：Excluded。

数据中心液冷 / Asetek thesis：Watchlist — Early Optionality / 缺 Asetek 并表收入、数据中心客户订单、合同金额+时间、中国市场适配、收入占比和商誉/债务压力验证。

公司整体：不进 Shortlist；若必须单桶处理，归为 Watchlist / 待核验。

## 8. R4-R6 已展开的失真点索引

### 8.1 公司级分桶 vs thesis-level 分桶

已展开至 a-share-r4-thesis-bucketing-announcement-calibration.md 8.1。 默认按 thesis-level 分桶，公司级只做 summary。

### 8.2 并购标的内部业务分层不足

已展开至 a-share-r5-ma-target-layering-smallcap-redflags.md 8.2。 并购标的业务分层规则见 R5 spec。

### 8.3 公告反证和降温话术仍需样本校准

已展开至 a-share-r4-thesis-bucketing-announcement-calibration.md 8.3。 6 级反证已给出判断标准 + 边界 + 校准流程 + 分桶矩阵, 见 R4 spec。

### 8.4 市场结构数据的最低证据标准未完全定义

已展开至 a-share-r6-market-structure-minimum-evidence.md 8.4。 R2/R3 最低数据包、缺数据处理和数据源优先级见 R6 spec。

### 8.5 公司级财务/治理红旗与 A 股重建四件尚未完全合流

已展开至 a-share-r5-ma-target-layering-smallcap-redflags.md 8.5。 公司级财务/治理红旗与风险覆盖规则见 R5 spec。
## 9. Worked Examples — 见 a-share-worked-examples.md

## 10. R9 Biotech BD 收入质量 — 见 a-share-r9-biotech-bd-quality.md
