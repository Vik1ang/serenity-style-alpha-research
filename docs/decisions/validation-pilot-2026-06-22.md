# Structural Alpha Skill Validation Pilot — 2026-06-22

目的：用一组“正例 / 边界例 / 反例”压力测试 `structural-alpha-research`，找出 skill 还需要补强的规则。本文是维护决策记录，不是 runtime reference，也不是投资建议或推荐名单。

## 样本选择原则

不要只找看起来最顺的票。验证篮子必须同时覆盖：

1. **高质量但已拥挤**：检验 skill 是否会把“好公司 / 好赛道”误判成仍有 alpha。
2. **财务传导清晰但暴露不纯**：检验 materiality 与 segment mix。
3. **周期真实但兑现期太长**：检验 1–4 quarter catalyst 是否足够硬。
4. **收入/订单高增长但单位经济差**：检验 low-base elasticity 是否被 backlog 叙事污染。
5. **客户集中 / 平台替代风险**：检验 comparative advantage 是否足够抗技术路线变化。

## 轻量样本篮子

> 时间戳：2026-06-22。市场价格/市值需在正式研究时重新拉取；这里仅用于 skill 压力测试。

| Ticker | 用途 | 初步测试结论 | 主要要验证的 skill 弱点 |
| --- | --- | --- | --- |
| CRDO | AI data-center connectivity / active electrical cables | 周期、需求、财务传导强；但估值和市场关注度已很高，适合测试“强基本面但未必强 alpha”的 cap | price-in / crowding gate、客户集中、铜缆 vs optical / CPO 路线替代 |
| ALAB | PCIe/CXL retimer、AI fabric / signal conditioning | 经营数据很强，但也是高关注高估值，适合测试“优质拥挤边界” | low-attention gate、平台绑定优势是否可持续、估值门槛 |
| VRT | 数据中心电力 / cooling / critical infrastructure | 一阶需求与现金流传导清晰；但已是共识龙头，适合测试 fully-consensus downgrade | backlog/orders 透明度、price-in、超大市值剩余弹性 |
| CLS | hyperscaler networking / AI compute manufacturing | 收入和利润传导强，估值相对不像纯 AI 半导体那么极端；但业务暴露需要拆 segment | materiality proxy、客户/项目集中、second-order exposure |
| COHR | photonics / datacom transceivers | 受益 AI datacom，但业务复杂、债务/整合/segment purity 需拆 | segment purity、margin repair、财务杠杆风险 |
| AAOI | 800G / 1.6T optical transceivers | 主题与周期强，股价/预期也强；亏损、客户/执行风险适合做红旗样本 | customer concentration、negative EPS、execution miss / firmware issue |
| MP | rare-earth magnet independence / policy cycle | 政策周期与物理供给约束清楚；但兑现期、政府交易结构、价格假设复杂 | catalyst horizon、policy-deal accounting、dilution / offtake quality |
| EOSE | zinc long-duration storage | backlog 与收入增长容易诱导“低基数弹性”误判；毛利/现金流/融资风险明显 | unit economics gate、financing-machine red flag、backlog quality |

## 本轮暴露出的改进点

### 1. 需要显式加入“验证篮子协议”

当前 skill 讲了筛选流程，但没有规定如何反向验证框架。建议后续在维护流程中固定：

- 每次大改 skill 后，至少跑 8 个样本。
- 样本必须含：2 个强正例、2 个拥挤边界、2 个暴露不纯/客户集中、2 个红旗反例。
- 输出不按“买不买”，只按“框架是否误判”记录。

### 2. Price-in / crowding gate 需要更硬

当前已有 “fully consensus” 降级规则，但实操上仍可能把高增长龙头写成强 alpha。建议补成硬规则：

- 若市值、估值、新闻密度、股价涨幅、机构关注度同时很高，结论默认降为 **Watchlist / 深挖对象**，除非能证明市场仍误分类。
- “好公司 / 好赛道 / 好业绩”不能替代 “低关注或错误定价”。

### 3. AI 供应链需要 customer concentration / architecture transition gate

CRDO、ALAB、AAOI、COHR 这类票的核心风险不是“AI 需求有没有”，而是：

- 单一 hyperscaler 或单一平台贡献过高。
- 800G → 1.6T → CPO / LPO / copper / optical 的路线切换导致优势迁移。
- 客户自研、双供、议价或认证切换。

建议在 domain extension 或 main SKILL 中把它设为 AI/半导体必填项。

### 4. Low-base elasticity 需要防止被 backlog 叙事污染

EOSE 这类样本说明：收入增长、订单 backlog、政策贷款都不能自动证明低基数修复。必须同时过：

- gross margin path；
- cash conversion；
- working-capital / capex need；
- external financing dependency；
- backlog cancellation / margin quality。

否则应被 capped at Watchlist / Excluded。

### 5. Catalyst horizon 需要更严格

MP 这类政策/资源/工业链票可能结构性正确，但兑现期常常超过 4 个季度。skill 应避免把“长期正确”写成“当前 alpha 候选”。

建议明确：

- 1–4 quarter catalyst 不明确 → 不能进 Shortlist，只能 Watchlist。
- 长周期政策项目需单列 “兑现期 / funding / permitting / construction / offtake quality”。

## 下一步建议

优先把上述改进合并为两处小改：

1. `SKILL.md`：增加 `Validation Protocol` 和更硬的 `Price-in / Customer concentration / Catalyst horizon` cap。
2. `references/cycle-objectivity-overlay.md`：增加 `Unit economics and backlog quality` 小节，防止低基数弹性误判。

暂不把具体 ticker 写入 runtime references，避免 skill 输出时把验证样本当成内置推荐。

## Evidence Pointers Used For This Pilot

- CRDO investor release, fiscal 2026 Q4/FY results: https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Technology-Group-Holding-Ltd-Reports-Fourth-Quarter-and-Fiscal-Year-2026-Financial-Results/default.aspx
- ALAB Q1 2026 results: https://www.asteralabs.com/news/astera-labs-reports-first-quarter-2026-financial-results/
- VRT Q1 2026 results: https://investors.vertiv.com/news/news-details/2026/Vertiv-Reports-Strong-First-Quarter-with-Diluted-EPS-Growth-of-136-Adjusted-Diluted-EPS-Growth-of-83-Raises-Full-Year-Guidance/default.aspx
- CLS Q1 2026 results: https://www.globenewswire.com/news-release/2026/04/27/3282031/0/en/celestica-announces-first-quarter-2026-financial-results.html
- COHR Q1 FY2026 results: https://www.coherent.com/news/press-releases/first-quarter-fiscal-year-2026-results
- AAOI Q1 2026 results: https://investors.ao-inc.com/news-releases/news-release-details/applied-optoelectronics-reports-first-quarter-2026-results
- MP Materials / DoD partnership: https://investors.mpmaterials.com/investor-news/news-details/2025/MP-Materials-Announces-Transformational-Public-Private-Partnership-with-the-Department-of-Defense-to-Accelerate-U-S--Rare-Earth-Magnet-Independence/default.aspx
- EOSE Q1 2026 results: https://investors.eose.com/news-releases/news-release-details/eos-energy-enterprises-reports-first-quarter-2026-financial
