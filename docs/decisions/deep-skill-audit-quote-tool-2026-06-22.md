# Deep Skill Audit With quote-tool — 2026-06-22

目的：用 `/Users/vik1ang/workbench/quote-tool` 对 `structural-alpha-research` 的优化做深度核对，重点看 A 股 market-context / price-in / R2-R3 / liquidity gates 是否能被本地行情数据实际支撑。本文是维护审计记录，不是 runtime reference，也不是投资建议。

## 1. quote-tool 可用性

已验证命令：

```bash
/Users/vik1ang/workbench/quote-tool/.venv/bin/quote quote 002463,300502,300308,601138,300476,688676,002130,920808 --json --pretty
/Users/vik1ang/workbench/quote-tool/.venv/bin/quote kline 002463 -d 60 --json --pretty
/Users/vik1ang/workbench/quote-tool/.venv/bin/quote margin 002463 --json --pretty
/Users/vik1ang/workbench/quote-tool/.venv/bin/quote industry --json --pretty
```

可直接支持的字段：价格、涨跌幅、5 日涨幅、60 日涨幅、成交额、换手率、量比、涨跌停价、是否涨停/跌停、PE_TTM、PB、PS_TTM、PCF_TTM、总市值、流通市值、融资融券、行业估值、60 日 K 线。

边界：

- `920808` 本轮返回 `no_data`，说明北交所/部分小票覆盖不能默认可用。
- `flow` 对沪电股份返回 0 值，需要谨慎使用，不能把资金流 0 当成无资金行为。
- `industry` 有行业代码和估值字段，但审计中没有行业名称映射，适合作相对估值原始数据，不适合作最终自然语言结论。
- quote-tool 不覆盖美股；美股/全球链条的行情数据仍需其他市场数据源。

## 2. A 股样本行情快照发现

原始输出保存在 `docs/decisions/quote-tool-audit-2026-06-22/`：

- `a-share-quotes.json`
- `a-share-quote-summary.json`
- `a-share-kline-summary.json`
- `kline-*.json`
- `margin-002463.json`
- `industry.json`

### 2.1 大市值 AI 硬件链已明显进入 crowding 检测区

截至 quote-tool 时间戳 `2026-06-22 15:43:53 Asia/Shanghai`：

| 代码 | 名称 | 市值档位 | 60 日涨幅 | 成交额 | 估值/拥挤字段 | 审计含义 |
| --- | --- | --- | ---: | ---: | --- | --- |
| 002463 | 沪电股份 | ≥1000 亿 | +100.17% | 132.9 亿 | PB 16.65 | 不能只写“PCB 基本面强”，必须触发 price-in / large-cap crowding 检查 |
| 300502 | 新易盛 | ≥1000 亿 | +88.88% | 263.1 亿 | PE 75.29 / PB 39.68 | 强业绩样本也应默认 Watchlist / 深挖，除非证明仍有误分类 |
| 300308 | 中际旭创 | ≥1000 亿 | +126.98% | 386.4 亿 | PE 103.13 / PB 43.32 / 5 日 +17.15% | R6 大市值 crowding 必须压过“光模块景气”叙事 |
| 601138 | 工业富联 | ≥1000 亿 | +27.80% | 233.2 亿 | PE 38.51 / PS 1.58 | 重点不在涨幅，而在代工价值捕获和巨额成交是否充分定价 |
| 300476 | 胜宏科技 | ≥1000 亿 | +27.95% | 179.8 亿 | PE 76.74 / PB 20.63 / 换手 5.7% | AI PCB 逻辑成立时仍需应收存货、现金流、price-in 双重 gate |

结论：skill 新增的 **Price-in / crowding cap** 是必要的。quote-tool 数据证明至少 5 个 A 股 AI 硬件样本不能直接进入“强 Alpha 候选”，必须先过 R6 市场结构。

### 2.2 中市值样本能测试“结构正确但未充分兑现”

| 代码 | 名称 | 市值档位 | 60 日涨幅 | 换手 | 审计含义 |
| --- | --- | --- | ---: | ---: | --- |
| 688676 | 金盘科技 | 100–1000 亿 | +3.00% | 5.02% | 方向真实但 price action 不拥挤；重点应放订单质量、SST 商业化、现金流/PCF |
| 002130 | 沃尔核材 | 100–1000 亿 | -22.34% | 3.36% | 市场结构不拥挤，但二阶暴露和技术路线替代是主要 gate |

结论：skill 的 **二阶暴露 cap** 和 **订单/backlog 质量 cap** 保留正确；不能用同一套大市值 crowding 规则简单压所有 A 股。

### 2.3 北交所/小票覆盖缺口必须显式写出

`920808` 在 quote-tool 中返回 `no_data`。这正好验证了 R6 的“缺数据先标不足”规则。后续回答涉及北交所或小票时，必须写：

> 当前行情数据源无覆盖 / 数据不足，不能硬判 R2/R3 或流动性风险解除。

## 3. 对 skill 的核对结论

### 已经优化正确的部分

1. **命名与定位**：`structural-alpha-research` 比旧的 person-style 命名更稳定，也避免了 IP/person dependence。
2. **核心链条**：cycle → demand → constrained supply → comparative advantage → low attention → value capture → catalyst → anti-thesis 足够完整。
3. **A 股独立栈**：R4/R5/R6 没有被全球框架覆盖；thesis-level、公司红旗和市场结构仍是 A 股核心。
4. **price-in gate**：quote-tool 行情证明这个 gate 必须硬化，尤其是新易盛/中际旭创/沪电/胜宏这类强基本面高拥挤样本。
5. **validation docs 放置**：样本放 `docs/decisions/` 正确，避免 runtime references 变成默认推荐池。

### 需要补强且已补强的部分

本次审计后已修改 `a-share-r6-market-structure-minimum-evidence.md`，新增 **行情快照字段包**：价格、市值、估值、5/60 日涨幅、成交额、换手、量比、涨跌停、20–60 日 K 线、融资融券/资金流/龙虎榜/异动公告/热榜，以及数据源无覆盖时的降级规则。

补充 review 发现：`output-template.md` 原先只写“最新市值 / 流动性备注”，会让 agent 把 R6 行情数据压缩成弱备注，无法稳定触发 price-in / R2-R3 判断。本次已把 Shortlist、Compact Triage 和 Compact Stock Screen 都改成显式要求行情快照与 R2/R3/拥挤判断。

### 仍不建议写入 runtime 的内容

不要把 `/Users/vik1ang/workbench/quote-tool` 绝对路径写进 runtime skill。原因：

- 这是本机工具，不是公开仓库的一部分；
- public skill 应保持可迁移；
- 运行时只需要规定“行情快照字段包”，具体工具可由用户环境决定；
- quote-tool 的原始审计结果已经放在 `docs/decisions/`。

## 4. 后续建议

1. 若希望这个 repo 长期绑定 quote-tool，可新增 `docs/local-data-tools.md`，而不是放进 runtime references。
2. quote-tool 可以增加美股支持或一个“market snapshot”命令，直接输出 skill 所需字段。
3. quote-tool 对北交所代码映射可增强；否则 A 股小票/北交所验证仍需备用数据源。
4. skill 后续可以增加一个 A 股输出模板，把行情快照字段固定到表格中。

## 5. Verification

- quote-tool 实时行情：成功，7/8 样本有数据；`920808` no_data。
- quote-tool 60 日 K 线：7/8 成功；`920808` no_data。
- quote-tool 融资融券：沪电股份样本成功。
- quote-tool 行业估值：成功但缺行业名称映射。
- skill basic validation：frontmatter name/description、hyphen-case、description trigger、frontmatter length 通过。
- canonical vs `.codex`：修改后已同步。
