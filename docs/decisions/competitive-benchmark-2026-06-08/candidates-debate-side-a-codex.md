# Codex 立场 A: 改/并入 (激进)

> 双盲 peer-discussion 第二轮, 支持"现在就把 candidates-2026-06-08.md 合并到 action plan 并触发 serenity 改动"
>
> 立场: **改 / 并入 / 现在动**。 本周先修入口索引, 本月把新候选证据并入 P0-2/3/4; R_{n+1}+ 仅登记边界, 不抢先实现。
>
> 写于: 2026-06-08 by Codex (gpt-5.5 xhigh) via oh-my-codex TUI in tmux agents:2.1
>
> 落盘原始: 3,454 bytes, 8 条理由, 298-403 字/条, 验证了 candidates.md + action plan + README + R4-R10 SHA

## A 立场 8 条理由

### A-1 先修索引，否则新增研究继续不可达

`candidates-2026-06-08.md:131-136` 已把新证据映射到 P0-2/3/4，`competitive-benchmark-action-plan.md:26-36` 确认 R9/R10 未纳入入口；`README.md:87,98-103` 仍停在 R4-R6。 现在应执行 P0-1，补齐 SKILL、FINAL、README 索引，否则研究越多，"规则存在但 agent 不加载"的债越大。

### A-2 Registry 是现有 P0-2 的证据升级

`candidates-2026-06-08.md:71-79,133` 用 Thesis OS 验证对象分离、失效条件和到期复核；`competitive-benchmark-action-plan.md:38-48` 已要求 thesis_id、状态机与 checkpoint。 现在应把字段并入同一 P0-2，不另建 registry；继续等待会让案例与复盘沿用临时格式，增加迁移成本。

### A-3 Citation 与数据状态应形成最小发布门禁

`candidates-2026-06-08.md:49-59,81-91,134-135` 给出 section 降级与 quality gate；`competitive-benchmark-action-plan.md:50-72` 已规定 P0-3/4 与 Registry 共同设计。 本月应落最小门禁：数字无引用、数据 stale/missing 或 filing 口径冲突时，证据块自动降级且不得支撑分桶。

### A-4 口径漂移应现在登记，暂不塞进 R5

`candidates-2026-06-08.md:43-47,140` 指出 KPI 定义、分部重组和非 GAAP 变化可伪造改善；`competitive-benchmark-action-plan.md:14-18` 要求新机制不破坏既有职责。 现在应将 comparability gate 登记到 R_{n+1}+，写清 owner 与触发条件，但不修改 R5 九阈值；登记防遗忘，实施留待案例校准。

### A-5 跨市场空白真实，但不属于本月实现

`candidates-2026-06-08.md:93-110,141-142` 表明港股、US/JP、crypto 不能共用研究合同；`competitive-benchmark-action-plan.md:104-140` 尚无跨市场项目。 现在只登记 adapters 与 crypto contract，禁止复用 equity materiality 阈值；本月先完成 Registry 公共字段。

### A-6 合并成本低于维持两份并行真相

`candidates-2026-06-08.md:122-151` 已完成优先级、吸收位置、后置事项和风险兼容判断；`competitive-benchmark-action-plan.md:22-140` 已有对应实施表。 合并只是为既有项目补候选来源、访问日期、字段与 backlog，约数小时；不合并会留下两份决策源，直接触发该计划 `:163` 的文档漂移风险。 应合并结论，不复制候选全文。

### A-7 风险约束应成为现在改动的验收条件

`candidates-2026-06-08.md:61-65,112-120,145-151` 已排除目标价、仓位、多 skill 粒度与外部框架替代；`competitive-benchmark-action-plan.md:156-164` 将 R-12~16 定为约束。 须做负面验收：不加买卖字段、不拆 24 skills、不覆盖 R4-R10、Registry 未稳定前不上 cron。

### A-8 计划现在合并，实施按两种速度推进

`candidates-2026-06-08.md:126-143` 已区分可吸收项与 R_{n+1}+；`competitive-benchmark-action-plan.md:168-190` 已确定节奏。 本辩论应落在 `references/`：本周修索引，本月设计 Registry/citation/status；完整 QA DAG、市场 adapters、crypto 与拆包待一季度样本后复评。
