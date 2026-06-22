# structural alpha-alpha 外部候选池 (2026-06-08)

> 来源: GitHub 主题页 + web 搜 + structural alpha 内部术语外部对应 + 跨市场空白
> 目的: 跟 2026-06-07 的 competitive-benchmark-action-plan.md (4 候选) 合并, 扩到 8-10 个候选
> **不写代码, 只列候选 + 差距分析**
>
> 口径: 共 10 个唯一候选, 其中已知 4 个、新增 6 个。方向 2/3 会复用方向 1 的候选做交叉对照, 不重复计数。

## 1. 已知 4 候选 (A 轮已扫, 这次确认/更新)

| 候选 | repo | 跟 structural alpha 差距 | 价值 |
|---|---|---|---|
| spikeHongg | [spikeHongg/china-stock-research-skills](https://github.com/spikeHongg/china-stock-research-skills) | 有母 skill、6 个核心模块、共享 citation/source registry 和 pattern selector；但没有 structural alpha 的 chokepoint 五因子、thesis-level 三桶、公告反证 6 级、R5 公司级阈值、R9 BD 收入质量、R10 大市值残余重估。 | **P0 (citation / routing 结构)** |
| belos-street | [belos-street/stock-analytics-skill](https://github.com/belos-street/stock-analytics-skill) | 24 skills 覆盖 A/H 股、ETF、基金、宏观、信用和资产配置，发现层也拆出量化/主题扫描；但粒度过细，且大量内容直接给加减仓、仓位和时机，不具备 structural alpha 的证据分桶与 anti-thesis gate。 | **P2 (discovery 隔离；24-skill 不照搬)** |
| yanglaiyang | [yanglaiyang/stock-analysis-skill](https://github.com/yanglaiyang/stock-analysis-skill) | 七步基本面框架、7 agents、15 类图表和稳定 Markdown/HTML 产物较完整；但没有 demand/bottleneck/materiality 硬 gate，也没有 thesis-level 反证覆盖，评分图表会把证据质量压成伪精确。 | **不入清单 (可视化)** |
| ZhuLinsen | [ZhuLinsen/daily_stock_analysis](https://github.com/ZhuLinsen/daily_stock_analysis) | 已扩展到 A/H/US、GitHub Actions、历史报告、回测和多渠道推送，并有数据源降级语义；但核心输出仍含买卖、点位、评分和策略信号，研究状态与交易信号没有按 structural alpha 的非投顾边界隔离。 | **P0 (数据状态)；自动化仅作后置参考** |

### spikeHongg

本轮确认其最强对应物仍是“关键事实可访问引用 + 官方披露优先 + 事实/解读/待验证分层”，可继续作为现有 P0-3 citation-standard 的结构参考。不可学之处是用通用中国股票模块替代 structural alpha 的五因子和 R4-R10；它解决的是研究编排，不是 chokepoint thesis 的入桶与反证校准。

### belos-street

本轮新增确认其 `hk-stock-analysis` 和本地港股行情能力可作为跨市场输入层样本，但不够构成港股版 structural alpha spec。可学的是 discovery 与 deep research 分离、按意图路由；不可学的是 24-skill 物理拆包和加减仓/仓位规则，继续受 R-12、R-13 约束。

### yanglaiyang

仓库当前仍把主要增量放在报告生成、图表和展示层。structural alpha 在 Registry、citation、block-level data status 尚未闭环前，不应优先吸收雷达图、热力图或评分可视化；最多保留“一页纸稳定 Markdown 决策记录”的 P2 思路。

### ZhuLinsen

本轮确认其跨 A/H/US、定时任务、通知渠道和失败降级能力继续增强，说明它适合验证未来 monitoring pipeline 的工程形态。但它的“买入/卖出/点位/评分”与 structural alpha 非投顾交易推演直接冲突；在 P0-2/3/4 跑稳前也不能倒序引入 cron，继续受 R-12、R-16 约束。

## 2. 方向 1 新候选 (GitHub topics, 3-4 个)

| 候选 | repo | 跟 structural alpha 差距 | 价值 (P0/P1/P2/不入) |
|---|---|---|---|
| CC Equity Research | [prof-little-bear/cc-equity-research](https://github.com/prof-little-bear/cc-equity-research) | 24 个 workflow、US/JP 数据、thesis tracker、reporting-quality drift 和 monitoring 较强；但偏传统机构研究桌面，没有 chokepoint 五因子的 shortlist gate，也没有 A 股公告反证/红旗/BD 专项。 | **P1** |
| AlphaAnalyst | [kbhujbal/AlphaAnalyst-open-source-autonomous-equity-research-agent](https://github.com/kbhujbal/AlphaAnalyst-open-source-autonomous-equity-research-agent) | citation validator、独立 Devil's Advocate、纯代码估值和硬 schema 强；但重型应用依赖多 API/数据库，只支持 US ticker，且没有 structural alpha 的 thesis 三桶和 A 股市场结构。 | **P0** |
| XVARY Stock Research | [xvary-research/claude-code-stock-analysis-skill](https://github.com/xvary-research/claude-code-stock-analysis-skill) | 有 data/model/quality/compliance/finalize 多级 gate、evidence-gap、challenge、kill criteria；但公开版隐藏阈值，结论仍是单公司 verdict/分数，不处理多 thesis 分桶或公告话术校准。 | **P0** |
| Claude Equity Research | [quant-sentiment-ai/claude-equity-research](https://github.com/quant-sentiment-ai/claude-equity-research) | 有 US equity 的基本面、催化、估值、bull/base/bear 和风险模板；但强制 BUY/SELL/HOLD、目标价、仓位和止损，引用仅是提示词要求，没有缺数据降级和 citation validator。 | **不入** |

### CC Equity Research

可学点不是其 24-skill 数量，而是两个具体机制。第一，`thesis-check` 要求按原始 pillar 检查，输出 Intact / Improved / Weakening / Broken，并把“事后换 thesis”本身视为问题；这与 R4 thesis-level 处理相近。第二，`reporting-quality` 检查 KPI 定义漂移、重分类、分部重组、非 GAAP 排除项漂移和选择性停止披露，并尽量按旧口径重算，能补 structural alpha 当前对“报表口径变化伪造增长/利润改善”的盲点。

不可直接照搬之处是其 tracker 仍包含 target price、stop-loss、increase/trim/exit 等动作字段，且 verdict 主要针对已持仓单 thesis，不等于 Shortlist / Watchlist / Excluded。其 US/JP 数据依赖 Drillr MCP；方法论可吸收，数据连接器不应成为 structural alpha 的硬依赖。

### AlphaAnalyst

最强可学点是可执行的引用失败语义：synthesizer 只允许使用预建 facts，所有数字必须带有效 `[F#]`；出现未知 tag 或“有数字无引用”时，对应 section 会被直接降级为 `Insufficient evidence`。这比“报告末尾列来源”更接近 structural alpha P0-3 + P0-4 所需的 block-level citation/data-status 契约。

其不同模型家族的 Devil's Advocate 和“LLM 只写、数字由代码计算”也值得进入验证样本。但整个项目是完整应用而非轻量 Markdown spec，且需要多家 API、Postgres/pgvector、Redis；structural alpha 应只吸收 schema/validator 语义，不吸收应用栈。

### XVARY Stock Research

XVARY 的公开 22-stage DAG 把 `data_quality_gate -> evidence_gap_analysis -> model_quality_gate -> triangulation -> challenge -> audit -> finalize` 串成发布前门禁，并明确检查 missingness、stale fields、broken units、filing coherence、contradiction 和 evidence sufficiency。它是本轮最接近“数据不足纪律 + 反证 gate + release gate”的外部对应物。

差距在于它的阈值、路由和 convergence 算法不公开，输出仍依赖 Constructive / Neutral / Cautious 与 0-100 分数；也没有 R4 的同公司多 thesis 覆盖关系、公告反证 6 级或 R9 的收入质量分解。建议吸收 gate 顺序和 kill-file 定义，不吸收评分。

### Claude Equity Research

该仓库适合作为负面对照：模板看似完整，包含财务、催化、估值、风险、技术面、期权和 insider，但命令文件强制输出 BUY/SELL/HOLD、价格目标、1%-5% 仓位和止损。它没有“关键数据缺失则降低结论上限”的执行规则，也没有把社媒/二手来源与法定披露分层。

因此不进入改进清单。它能提醒 structural alpha：免责声明不能修复输出层的投顾化；R-12 必须约束字段本身，而不是只在报告末尾写 “not financial advice”。

## 3. 方向 2 候选 (structural alpha 内部术语外部对应, 2-3 个)

| 候选 | repo | 哪些内部术语有外部对应 | 价值 |
|---|---|---|---|
| Thesis OS | [youngseongshin/thesis-investment-os](https://github.com/youngseongshin/thesis-investment-os) | thesis-level 对象、evidence/action/prediction/feedback 分离、invalidation、native horizon、Devil's Advocate、数据质量 failure mode | **P0 (P0-2 Registry 的强验证样本)** |
| AlphaAnalyst | [kbhujbal/AlphaAnalyst-open-source-autonomous-equity-research-agent](https://github.com/kbhujbal/AlphaAnalyst-open-source-autonomous-equity-research-agent) | 数据不足纪律、数字引用硬校验、无证据 section 自动降级、独立反方 agent | **P0 (P0-3/4)** |
| XVARY Stock Research | [xvary-research/claude-code-stock-analysis-skill](https://github.com/xvary-research/claude-code-stock-analysis-skill) | data quality gate、evidence gap、adversarial challenge、kill-file、stale/missing 检查 | **P0/P1 (gate 结构直接吸收；完整 QA DAG 后置)** |

### Thesis OS

Thesis OS 与 structural alpha 的最近对应不是选股公式，而是对象模型：`Evidence` 带 source/date/confidence，`Thesis` 带 assumptions/evidence_ids/invalidation/status/type/horizon，`Prediction` 预注册 evaluation due，`Feedback` 分 process score 与 result score。它还明确“screener 只生成 candidate，不是答案”，可直接验证 P0-2 Candidate Registry 与 P2-9 discovery prior 隔离。

差距是它没有 Shortlist / Watchlist / Excluded 的硬 entry/auto-exclude 规则，也没有 R4 公告反证 6 级、R5 九阈值或 R9 BD 收入质量。应把它当生命周期和审计层参考，不能替代 structural alpha 的判断层。

### AlphaAnalyst

它提供了本轮最具体的“数据不足纪律”外部实现：不是整篇免责声明，而是逐 section 检查数字和引用；失败 section 自动降级，并保留失败原因。这个机制可映射到 P0-4 的 `missing/stale/fallback/estimated/partial/fetch_failed`，也可要求决定分桶的 evidence block 同时通过 citation validator。

它的 Devil's Advocate 是 agent 级反方，不是 R4 的公告话术等级；因此只能补“反方独立性”，不能作为公告反证 6 级的替代证据。

### XVARY Stock Research

XVARY 把低质量输入阻断、证据缺口搜索、模型 sanity check、跨模块矛盾、反方挑战和发布审核分开，能防止一个笼统的“质量检查”同时承担所有职责。对 structural alpha 最实用的映射是：先判数据状态，再判 evidence sufficiency，再做 anti-thesis，最后才允许进入 Shortlist/交易推演。

但其 company-level kill-file 仍是通用类别，没有公开类似 R5 的九个公司级硬阈值；也没有 Biotech BD 或大市值 re-rating residual 的专门 gate。

## 4. 方向 3 候选 (跨市场空白, 1-2 个)

| 候选 | repo | 跨市场 (港/美/加密) 哪块 | 价值 |
|---|---|---|---|
| LLMQuant Skills | [LLMQuant/skills](https://github.com/LLMQuant/skills) | 独立 crypto router + tokenomics/usage/unlocks/liquidity/funding/on-chain gate；另有 US filing/13F/crowding workflow | **P1；crypto 属 R_{n+1}+** |
| CC Equity Research | [prof-little-bear/cc-equity-research](https://github.com/prof-little-bear/cc-equity-research) | US + Japan equities/ADRs，SEC filings、供应链、thesis tracking、catalyst calendar | **P1；美股/日股方法参考** |

### LLMQuant Skills

LLMQuant 的价值是已经把 crypto 当独立资产范畴，而不是把股票模板换 ticker。其 token workflow 明确检查 token 经济权利、circulating/FDV、unlock、holder concentration、TVL/fees/users、bridge/smart-contract/regulatory/counterparty risk，并写明“token ownership 不等于 protocol equity”“缺 tokenomics/usage 数据时不得做依赖它们的估值结论”。这正是 structural alpha 若扩 crypto 必须新建 domain contract 的原因。

其 equities workflow 也要求 filing period、price window、13F period、stale notice 和 missing-section fallback，可作为美股 evidence contract 参考。不可直接吸收的是其 18-category skill 规模和单一 LLMQuant Data 依赖；structural alpha 应抽象数据能力和 fallback，不绑定特定 MCP。

### CC Equity Research

该仓库覆盖 US、Japan 和 ADR，且供应链 discovery、SEC/IR/政府数据、thesis tracker、catalyst calendar 比 structural alpha 当前的跨市场入口更完整。可借鉴美股的 filing-first、季度 thesis check、reporting-definition drift，以及日本公司数据源/币种/披露节奏的显式处理。

它仍没有港股通/南向资金、HKEX 公告、同股不同权、VIE、配售折价、基石/控股股东、停牌复牌等港股特有风险。港股不能仅靠其 US/JP 模板补齐；belos-street 和 ZhuLinsen 只证明数据可取，也没有形成港股版 R4-R10。

## 5. 排除 (重复 / 1:1 fork / 不可用)

- [muxuuu/structural alpha-skill](https://github.com/muxuuu/structural alpha-skill) — structural alpha 方法的直接衍生/复刻，不作为独立外部证据。
- [lanfuli/aleabito-structural alpha-skills](https://github.com/lanfuli/aleabito-structural alpha-skills) — 同类 structural alpha 复刻，不能用于证明外部方法独立收敛。
- [generatedgallerybot/awesome-source-aware-stock-research](https://github.com/generatedgallerybot/awesome-source-aware-stock-research) — 仓库极小且更像自动生成索引，没有可核验的完整 framework。
- [Stewyboy1990/stockscope-mcp](https://github.com/Stewyboy1990/stockscope-mcp) — 已 archived，且主要是 MCP 数据接口，不是选股/反证 spec。
- [riazarbi/sp500-scraper](https://github.com/riazarbi/sp500-scraper) — S&P 500 成分历史数据集，不是 LLM agent research framework。
- `ftokarek/*-Equity-Research` 等单公司报告仓库 — 可作案例材料，但不是可复用 skill/spec，不计入候选。
- `quant-sentiment-ai/claude-equity-research` 虽保留在 10 候选中作负面对照，但明确不建议合并：直接输出评级、目标价、仓位和止损，违反 R-12。

## 6. 总结: 合并到 competitive-benchmark-action-plan 的建议

### 候选优先级

- **新增 P0 参考 3 个**：AlphaAnalyst、XVARY、Thesis OS。
- **新增 P1 参考 2 个**：CC Equity Research、LLMQuant Skills。
- **新增 P2 0 个**：本轮没有比既有“一页纸产物 / discovery prior”更独立的低优先级机制。
- **新增不入 1 个**：Claude Equity Research；另排除 fork、数据集和单公司报告。

### 可直接吸收到既有 action plan

1. **P0-2 Candidate Registry**：吸收 Thesis OS 的 `Evidence -> Thesis -> Prediction -> Feedback` 对象分离、`source_date/collected_at/confidence`、`invalidation`、`native_horizon/evaluation_due`、process/result 分离。不要另建一套 registry。
2. **P0-3 Citation**：吸收 AlphaAnalyst 的 section-level validator：未知 citation、数字无 citation、无事实支撑时，段落必须降级并保留原因。
3. **P0-4 Data Status**：吸收 XVARY 的 gate 顺序和检查项：missing/stale/unit/filing coherence -> evidence gap -> contradiction/evidence sufficiency -> release gate。
4. **P2-9 Discovery prior**：用 Thesis OS 的 “screener candidate is not an answer” 作为外部验证，继续禁止 discovery score 提升 Shortlist conviction。

### 需要进入 R_{n+1}+ 的范畴

- **Reporting-definition drift / comparability gate**：来自 CC Equity Research。需要单独处理 KPI 定义漂移、重分类、分部重组、非 GAAP exclusion drift、选择性停止披露和旧口径重算；不宜塞进 R5 九阈值。
- **Crypto token/protocol contract**：来自 LLMQuant。tokenomics、unlock、holder concentration、on-chain usage、bridge/smart-contract risk 与上市公司 equity materiality 不是同一对象模型，必须独立 domain extension。
- **US/JP/HK market adapters**：SEC/13F、Japan disclosure、HKEX/南向/VIE/配售/停牌规则应按市场拆 reference；不能只在主 SKILL 增加一个 region 参数。
- **完整 adversarial/release QA DAG**：XVARY 的 22-stage 全量流程偏重。先把最小 gate 写入 P0-2/3/4，跑样本后再判断是否新增独立 QA reference。

### 与 R-12~16 的兼容性

- **R-12 不学买卖信号**：AlphaAnalyst/Thesis OS/XVARY 只吸收 evidence、lifecycle、gate；不吸收 action、target、position sizing。Claude Equity Research 明确不入。
- **R-13 不照抄多 skill 粒度**：CC Equity Research 24 workflows、LLMQuant 18 categories 只证明路由可模块化，不触发 structural alpha 立即拆包。
- **R-14 不削弱现有强项**：外部 gate 只能包裹 R4 thesis-level、公告反证、R5 红旗、R9 BD、R10 re-rating，不能替换。
- **R-15 防文档漂移**：若后续吸收，必须记录 repo URL、具体文件、访问日期和适用边界。
- **R-16 Registry 先于 cron**：Thesis OS 再次支持该顺序；ZhuLinsen 的自动化能力仍只能后置。

## 7. 调研方法 + 引用

### GitHub topics / 搜索入口

- [topic: stock-research](https://github.com/topics/stock-research?o=desc&s=updated)
- [topic: investment-research](https://github.com/topics/investment-research?o=desc&s=updated)
- [topic: equity-research](https://github.com/topics/equity-research?o=desc&s=updated)
- [topic: ai-agents-finance](https://github.com/topics/ai-agents-finance?o=desc&s=updated)

### 关键规则文件

- CC Equity Research: [README](https://github.com/prof-little-bear/cc-equity-research/blob/main/README.md), [Thesis Tracker](https://github.com/prof-little-bear/cc-equity-research/blob/main/anthropic-equity-research-skills/thesis-tracker/SKILL.md), [Thesis Check](https://github.com/prof-little-bear/cc-equity-research/blob/main/community-skills/monitor/thesis-check.md), [Reporting Quality](https://github.com/prof-little-bear/cc-equity-research/blob/main/community-skills/analyze/reporting-quality.md)
- AlphaAnalyst: [README](https://github.com/kbhujbal/AlphaAnalyst-open-source-autonomous-equity-research-agent/blob/main/README.md), [citation/downgrade synthesizer](https://github.com/kbhujbal/AlphaAnalyst-open-source-autonomous-equity-research-agent/blob/main/backend/src/agents/synthesizer.py)
- XVARY: [README](https://github.com/xvary-research/claude-code-stock-analysis-skill/blob/main/README.md), [SKILL](https://github.com/xvary-research/claude-code-stock-analysis-skill/blob/main/SKILL.md), [methodology](https://github.com/xvary-research/claude-code-stock-analysis-skill/blob/main/references/methodology.md)
- Thesis OS: [README](https://github.com/youngseongshin/thesis-investment-os/blob/main/README.md), [models](https://github.com/youngseongshin/thesis-investment-os/blob/main/thesis_os/models.py), [judgment loop](https://github.com/youngseongshin/thesis-investment-os/blob/main/docs/judgment-loop.md), [design principles](https://github.com/youngseongshin/thesis-investment-os/blob/main/docs/design-principles.md)
- LLMQuant: [README](https://github.com/LLMQuant/skills/blob/master/README.md), [contribution/evidence contract](https://github.com/LLMQuant/skills/blob/master/CONTRIBUTING.md), [crypto router](https://github.com/LLMQuant/skills/blob/master/skills/llmquant-crypto/SKILL.md), [token research](https://github.com/LLMQuant/skills/blob/master/skills/llmquant-crypto/workflows/crypto-token-research.md), [equity memo](https://github.com/LLMQuant/skills/blob/master/skills/llmquant-equities/workflows/equity-research-memo.md)
- Claude Equity Research: [README](https://github.com/quant-sentiment-ai/claude-equity-research/blob/main/README.md), [research command](https://github.com/quant-sentiment-ai/claude-equity-research/blob/main/commands/trading-ideas/commands/research.md)

### 可复用 query

```text
GitHub repository search:
topic:stock-research
topic:investment-research
topic:equity-research
topic:ai-agents-finance

Repo 内机制检索:
"data quality gate" OR "evidence gap" OR "insufficient evidence"
"thesis tracker" OR invalidation OR "devil's advocate"
"citation validator" OR "numerical content without source"
freshness OR stale OR fallback OR missing
tokenomics OR unlocks OR "holder concentration"
"reporting quality" OR "definition drift" OR reclassification
```

调研日期为 2026-06-08。判断优先使用 repo README、SKILL/workflow、schema/validator 源文件；GitHub topic/description 只用于发现，不单独作为强结论证据。

## 8. 仍未覆盖的失真点

1. **公告反证 6 级仍无外部一一对应物**：外部常见的是 generic bear case、Devil's Advocate 或 kill criteria，没有按“完全否认/无规模化/占比低/不确定/未收入/业务正常”校准公告措辞与 thesis 分桶。
2. **R5 公司级 9 阈值红旗仍较独有**：外部 repo 多列风险或做 data/model quality gate，未找到公开、可执行且覆盖财务/治理/融资/商誉/客户集中等九阈值的同构规则。
3. **R9 Biotech BD 收入质量 gate 无对应物**：未找到同时拆 upfront、near-term milestone、development/sales milestone、royalty、自营销售，并把“资产验证”与“持续盈利”分桶的公开 agent spec。
4. **R10 大市值 re-rating 残余未被解决**：外部有 valuation drift、variant perception、street expectations、13F/crowding，但没有把已实现涨幅、估值扩张、机构共识与剩余基本面兑现系统组合成 residual gate。
5. **港股专属研究合同仍空白**：已有 repo 能取港股数据或做通用分析，但未找到 HKEX 公告优先级、南向资金、VIE/同股不同权、配售/供股、基石/控股股东、停牌复牌与流动性折价的完整 LLM skill。
6. **跨市场统一但不混淆对象的 Registry 尚无现成答案**：equity thesis、Biotech asset、crypto token/protocol、事件驱动和大市值重估需要共享 evidence/status 生命周期，但 materiality、风险和失效条件不能共用同一套阈值。
