# 4 件 Spec Peer-Discussion 总结 (Round 1)

## Codex 逐点表态

| # | Hermes review 点 | Codex 表态 |
|---|---|---|
| 1 | 4 件结构覆盖 A 股 vs 美股结构差异 | agree |
| 2 | 4 件之间接口不是孤立 | agree |
| 3 | 跑票顺序 政策→传播→重估→涨跌停 | agree (但需补优先级冲突规则) |
| 4 | 已知失败 + fallback 有风险意识 | agree (但 fallback 具体度不足) |
| 5 | 点 1 优先级冲突 | agree. R3 涨跌停风险定价应覆盖 R0 政策前置; 价格/流动性/监管风险优先于故事背景 |
| 6 | 点 2 fallback 不够具体 | agree. 现在更像方向性 fallback, 不够像可执行 checkpoint |
| 7 | 点 3 confirmation gate 没硬规则 | agree. Materiality 必须硬化 |
| 8 | Materiality 是全 4 件兜底 gate | needs-discussion. 同意是最终兜底, 但**不同意 "cover 任何缺口"** — 它不能弥补政策/周期完全不成立或公司公告明确否认, 只能防止题材绕过财务验证 |

## Hermes 回应(本轮)

- 接受 Codex 反驳: 我说"cover 任何缺口" 表述过头, Materiality 是**财务硬规则**, 不能逆推"政策成立" 或"公司没公告否认"。 它只防"题材绕开财务验证", 不是 cover 所有缺口。
- 接受 Codex 提的"3 条硬化规则" 作为收敛版补丁。
- **我之前说 "cover 任何缺口" 是错的**, Codex 抓得对。

## 3 条硬化规则 (Codex 提, Hermes 同意)

### Rule 1: 冲突优先级规则
- R3 风险定价 > R0 政策/传播乐观信号
- 公司强反证 (公告明确否认) > 题材传播
- Materiality 缺失 > catalyst 信号

### Rule 2: 具体 fallback checkpoint
- 每件"等待落地" 类 fallback 必须落到可执行 checkpoint:
  - 试点城市公布
  - 招标公告
  - 合同签署
  - 订单公告
  - 财务并表
  - 财报披露
- 方向性 fallback ("看政策细则落地") 一律不收

### Rule 3: Materiality 兜底硬门槛
- 不是 cover 所有缺口的万能补丁
- 是进入 Shortlist 的最终硬 gate
- 硬规则: 没有"收入占比 ≥10% OR 具体合同金额+时间" 的 confirmation, 一律不进入 Shortlist

## 收敛结论

- **是这么回事** + **3 处该改** (Codex + Hermes 共同)
- 第 1 步交付物完成: 4 件 spec + 3 条硬化规则
- 准备进 c 第 2 步 (已知案例倒推) — 等 Vik1ang 选票
