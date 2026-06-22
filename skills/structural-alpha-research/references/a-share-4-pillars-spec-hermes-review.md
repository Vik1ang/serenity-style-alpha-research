# Hermes 独立 Review(未读 self-review, 避免锚定)

## 同意
- 4 件结构: 政策前置 / 倒序信息传播 / 重估触发路径 / 涨跌停风险定价 — 这 4 件确实覆盖 A 股 vs 美股的结构差异
- 4 件之间接口: 每件都跟其他 3 件有连接, 不是孤立
- 跑票顺序: 政策→传播→重估→涨跌停, 对
- 失败 fallback: 每件都列了 3-5 种已知失败 + fallback, 风险意识到位

## 不同意 / 需要讨论

### 点 1: 优先级冲突没处理
- 问题: 政策刚出(R0 政策前置), 但股票已经 5 连板(R3 涨跌停定价), 应该听政策 R0 还是涨跌停 R3?
- Codex spec 里没明说
- 我会假设 R3 胜出(价格不可逆, 风险定价优先), 但应该在 spec 里写明

### 点 2: fallback 段不够具体
- 例: 第 1 件政策前置的 fallback "看政策细则落地" 太泛
- 应该给 "落地三步: 试点城市公布 → 龙头公司收到订单 → 财报或合同披露" 才算可执行
- 现在 c 第 3 步跑票时, 没具体 fallback 就无法判断 policy/cycle R0 vs R1 的过渡

### 点 3: 第 3 件 confirmation gate 没硬规则
- self-review 提到的 "Materiality 应该是 confirmation 的硬子 gate", 我同意
- 但 spec 里没写"硬"字, 只写了"如果 catalyst 出现但 confirmation 未跟上" 这种条件式
- 应该是硬规则: 没有 "收入占比 ≥ 10% OR 具体合同金额+时间" 的 confirmation, 一律不进入 Shortlist

## 1 处该改(跟 self-review 撞了, 但角度不同)
- self-review: Materiality 应该是 confirmation 的**硬子 gate**
- 我同意 + 加一点: 不只是 confirmation 的硬子 gate, 还是**全 4 件的兜底 gate** — 如果 4 件里任何一件没满足, Materiality 必须能 cover 那个缺口

## 结论
- 大方向同意("是这么回事")
- 3 个点需要讨论(优先级冲突 / fallback 具体度 / Materiality 硬度)
- 加 1 点: Materiality 是兜底 gate, 不只是 confirmation 子 gate
