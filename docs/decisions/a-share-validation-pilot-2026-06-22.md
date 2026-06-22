# A-share Structural Alpha Skill Validation Pilot — 2026-06-22

目的：补充 A 股验证篮子，测试 `structural-alpha-research` 是否能在 A 股语境下正确处理 thesis-level 分桶、公告反证、市场结构、题材拥挤、公司级财务红旗和低基数/订单质量。本文是维护决策记录，不是 runtime reference，也不是投资建议或推荐名单。

## A 股验证篮子原则

A 股不能只用“产业链逻辑正确”的样本验证。每次验证至少覆盖：

1. **确认型强基本面样本**：需求、瓶颈、收入、利润传导都较清楚，用来测试是否仍会被 price-in cap 降级。
2. **高关注拥挤样本**：业绩强但已被市场充分交易，用来测试 R6 市场结构与大市值 crowding。
3. **二阶/三阶暴露样本**：公司确实相关但价值捕获链条较长，用来测试 exposure purity。
4. **多 thesis / 题材混炒样本**：同一家公司多个概念并行，用来测试 R4 thesis-level 分桶。
5. **订单/扩产/政策样本**：防止把订单、产能或政策支持直接当作现金流和利润确认。
6. **小票/北交所/流动性样本**：测试涨跌停、换手、流动性和公告反证对 Shortlist 的杀伤力。

## 样本篮子

> 时间戳：2026-06-22。正式研究时必须重拉价格、市值、流通市值、最近 5–10 日涨跌停/成交额/换手、异动公告和最新财报。这里仅用于 skill 压力测试。

| Ticker | 用途 | 初步测试结论 | 主要要验证的 skill 弱点 |
| --- | --- | --- | --- |
| 沪电股份 002463 | AI 服务器 / 高速交换机 PCB | 公司披露数据通讯 PCB、AI 服务器/HPC、高速交换机收入，基本面传导较清楚；适合做 A 股确认型样本 | price-in / 大市值 crowding、客户集中、产能扩张与现金流 |
| 新易盛 300502 | 高速光模块 / 800G / 1.6T | 收入、利润、现金流都很强，但总市值和关注度极高；适合测试“强龙头不等于低关注 alpha” | R6 大市值 crowding、库存/汇兑/客户集中、技术路线切换 |
| 中际旭创 300308 | 高端光模块 | 产品和客户方向清楚，市场共识极强；适合测试 price-in cap 与全球客户集中 | fully-consensus downgrade、800G/1.6T 迭代、海外客户集中 |
| 工业富联 601138 | AI 服务器 / 云计算代工 | AI 服务器收入体量大，但代工模式毛利率较低，适合测试“收入巨大但价值捕获有限” | second-order exposure、低毛利、客户/平台依赖、材料成本传导 |
| 胜宏科技 300476 | AI PCB / 高端 PCB | 业绩高增，但公开报道提示库存/产销质量需看；适合测试订单/收入质量与 cash conversion | 应收存货、产销匹配、gross margin sustainability、price-in |
| 金盘科技 688676 | AIDC 干式变压器 / 固态变压器 | 数据中心电力方向真实，已有 AIDC/IDC 销售和订单线索；但新技术和订单兑现期需拆 | 订单质量、SST 商业化时间、1–4Q catalyst、交付/毛利质量 |
| 沃尔核材 002130 | 高速铜缆 / 高速通信线 | 有高速通信线量产与增长线索，但部分 AI 暴露是间接供货，技术路线风险明显 | 二阶暴露、客户链条、copper vs optical/CPO 路线替代 |
| 曙光数创 920808 / 中科曙光液冷链 | 数据中心液冷 | 产品历史和液冷技术路径清楚，但北交所/小票流动性、订单兑现和客户收入需严查 | 小票 liquidity、订单/收入确认、thesis-level 分桶、R2/R3 |

## 暴露出的 A 股专属改进点

### 1. A 股验证不能只看产业逻辑，必须同步跑 R6 市场结构

新易盛、中际旭创、沪电股份这类样本会让框架天然写出“强基本面”。但 A 股结论还必须回答：

- 市值档位是否已进入大市值 crowding；
- 是否已被机构和散户共同充分定价；
- 最近是否出现热榜、放量、异动公告或题材复盘高度集中；
- 是否还有“错误分类”，而不是只剩“持续兑现”。

### 2. 二阶暴露要比美股更严格

工业富联、沃尔核材这类样本说明：A 股主题传播常把“供应链相关”直接讲成“瓶颈受益”。skill 应明确：

- 代工收入不等于高价值捕获；
- 间接供应不等于客户锁定；
- 客户订单饱满不等于上市公司 segment materiality；
- 技术路线迁移会让二阶供应商最先失去溢价。

### 3. 订单、扩产、新技术样机都不能跳过兑现质量

金盘科技、曙光数创这类样本说明：AIDC / 液冷 / 电力设备方向真实，但不能用订单或样机直接替代：

- 合同金额与交付窗口；
- 收入确认口径；
- 毛利率和现金流质量；
- 是否需要继续 capex / 存货 / 应收支撑；
- 是否存在客户试点、认证或并网/验收不确定性。

### 4. 同一公司必须拆 thesis，不然 A 股最容易误判

A 股公司常同时挂 AI、机器人、液冷、铜缆、数据中心、电力设备等多个标签。验证时必须按：

> 公司 × 业务入口 × 客户/应用场景 × 时间窗口 × 证据状态

逐条分桶。一个 thesis 的收入确认，不能自动支持另一个 thesis；一个 thesis 被公告否认，也不能自动否认全部公司。

### 5. A 股验证需要记录“非推荐”边界

验证样本很容易被误读成候选池。维护规则应明确：

- `docs/decisions/*validation-pilot*` 只记录 framework failure modes；
- 不进入 runtime references；
- 不作为后续回答默认 ticker；
- 正式研究仍必须重新拉取市场数据、公告和财务。

## 建议合并到 runtime 的小改

1. `SKILL.md` 的 Validation Protocol 增加 A 股专用要求：A 股验证篮子必须覆盖 thesis-level、R2/R3 市场结构、二阶暴露、订单质量、小票流动性。
2. `a-share-skill-spec-FINAL.md` 增加 “A 股 framework validation” 小节，明确验证样本只入 `docs/decisions/`，不进入 runtime references。

## Evidence Pointers Used For This Pilot

- 沪电股份 2025 年报摘要 / 数据通讯 PCB、AI 服务器和 HPC 收入：https://static.cninfo.com.cn/finalpage/2026-03-25/1225027831.PDF
- 新易盛 2025 年报与 2026 一季报公开报道：https://www.stcn.com/article/detail/3795816.html
- 新易盛库存/一季报边界报道：https://www.nbd.com.cn/articles/2026-04-24/4356482.html
- 中际旭创 2025 年报摘要：https://pdf.dfcfw.com/pdf/H2_AN202603301820868498_1.pdf
- 工业富联 2025 年报公开页面：https://money.finance.sina.com.cn/corp/view/vCB_AllBulletinDetail.php?id=11990023&stockid=601138
- 胜宏科技 2025 年报公开页面：https://money.finance.sina.com.cn/corp/view/vCB_AllBulletinDetail.php?id=11993270&stockid=300476
- 金盘科技 2025 年报摘要：https://static.cninfo.com.cn/finalpage/2026-03-21/1225021764.PDF
- 金盘科技数据中心订单报道：https://www.stcn.com/article/detail/3565008.html
- 沃尔核材高速通信线量产/一季度增长报道：https://www.stcn.com/quotes/index/sz002130.html
- 曙光信息 2025 年报摘要 / 曙光数创液冷业务：https://static.cninfo.com.cn/finalpage/2026-04-15/1225104563.PDF
