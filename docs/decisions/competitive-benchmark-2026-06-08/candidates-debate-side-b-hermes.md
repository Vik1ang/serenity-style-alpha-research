# Hermes 立场 B: 不并入 / 不修改 (保守)

> 双盲 peer-discussion 第二轮, 反对"现在就把 candidates-2026-06-08.md 合并到 competitive-benchmark-action-plan 并触发 structural alpha spec 改动"
>
> 立场: **不改 / 不并入**, 候选池继续当参考池, 等 1 季后再评估
>
> 跟 memory 里"Vik1ang 2026-06-07 纠正: 研究外部 skill 和修改自家 skill 不能同日混。 跳步算拖"是同源

## B 立场 8 条理由

### B-1 candidates.md 跟 competitive-benchmark-action-plan.md 是同源对照物, 不是新信号
candidates-2026-06-08.md 跟 2026-06-07 扫描的 4 候选 (spikeHongg / belos-street / yanglaiyang / ZhuLinsen) **同属"外部对照物"**。 合并这两个, 等于"把参考池扩到 10 个", 但**不产生任何新执行项**——action plan 里的 P0-2/3/4 / P1-5/8 / P2-6/9/10 都没动, 只多了 6 个候选做"未来候选"。
**风险**: 合并让用户觉得"action plan 更新了 = 进度", 但实际是 reference 文件版本号涨了, 没有任何 spec 落地。

### B-2 3 个 P0 新候选 (AlphaAnalyst / Thesis OS / XVARY) 跟现有 P0-2/3/4 是"对应"不是"新增"
- AlphaAnalyst 的"引用失败自动降级" → 已经是 P0-3 Citation 的子集
- Thesis OS 的 Evidence/Thesis/Prediction/Feedback 物件模型 → 已经是 P0-2 Registry 的设计原则
- XVARY 的 22 阶段 DAG → 已经是 R6 数据不足纪律 + R4 反证 + Shortlist 门禁顺序的拼装
**这些不是新 P0, 是"现有 P0 的外部验证样本"**。 合并会产生"9 项 → 9 项 + 3 项外部样本引用"的膨胀, 不增加执行项。

### B-3 3 个 P0 候选里 2 个 (AlphaAnalyst / XVARY) 是"重型应用"不是"轻量 Markdown spec"
- AlphaAnalyst 需要 Postgres + pgvector + Redis + 多家 API + Claude 3 家模型 → **应用栈, 不是 skill**
- XVARY 的 22 阶段 DAG 阈值/路由/convergence 算法**不公开** → 黑箱, 不可吸收
**可学的只有 schema/validator/gate 顺序, 不能照搬**。 "新增 P0 参考 3 个" 这种合并会**误把不可学标成 P0**。

### B-4 R-12 硬约束在 Claude Equity Research 出现 1 次 + 已经在 action plan 第 160 行
R-12 已经写进 action plan 第 160 行 (5 项风险约束, R-12=不学 ZhuLinsen 买卖信号)。 合并 candidates.md 不会强化 R-12, 只会在文件里**多一处证据**, 但 R-12 本身不动。 真正有意义的 R-12 强化是"SKILL.md 顶层把 R-12 写成机器可读约束"——这跟 candidates.md 无关。

### B-5 candidates.md 第 138-144 行说"需要进入 R_{n+1}+ 范畴"
Codex 自己说: "需要进入 R_{n+1}+ 范畴: 反向影响现存 R4-R10 的部分; LLMQuant 跨资产扩展; 港股合同"。 **R_{n+1}+ 是结构改动, 风险高, 跳到 R_{n+1}+ = 跳 P0 跑 (跳步)**。 跟 memory 2026-06-07 "Vik1ang 纠正: 跳步算拖" 是一回事。

### B-6 港股 / 美股 / 加密是空白, 但 blank ≠ urgent
structural alpha 当前定位: A 股 + chokepoint alpha。 港股 (belos-street 有数据但缺 R4-R10) / 美股 (CC Equity Research, AlphaAnalyst 都强但 US 模板不能直接套 A 股) / 加密 (LLMQuant 强但 tokenomics ≠ 股票) 都**不是"现在就要"**。
真正"现在就要" 的: 港股 = 不是 (structural alpha 用户跑 A 股); 美股 = 已经是 structural alpha (public bottleneck-alpha) 主战场, 抄她就行, 不用自己造。 **空白是设计选择, 不是缺口**。

### B-7 competitive-benchmark-action-plan.md 已有 9 项 + 5 项风险约束, 再加 6 候选 = 15 项
action plan 从 9 项涨到 15 项, 跟 4 候选的 9 项是同一个量级问题: **候选越多, 用户越难决策**。 真正能落地的是 4 项 P0 (本周 1 + 本月 3), 候选池是参考, 不是 todo list。

### B-8 这次辩论触发条件不是 candidates.md 出现, 是 "执行时遇到新坑"
- 2026-06-07 跑 R9 暴露 C3 二义性 → 当下拆 C3a/C3b
- 2026-06-05 跑光迅科技 → 当下加 R3 reconcile 矩阵规则
- 每次都是"跑票踩坑 → 改 spec", 不是"读外部 repo → 改 spec"
**等下次跑票 (R11 起 frame) 遇到新坑, 再回头看 candidates.md 里有没有对应补丁**, 比现在合并更稳。

## B 立场总结

**不改, 候选池继续当 reference**。 等 1 季后 (跑稳 P0-2/3/4 + 1-2 轮 R11) 再回头评估"哪些外部候选要并入 action plan"。

**最大代价**: 候选池**没有官方 owner**, 万一忘了一年没人维护。 缓解: 把 candidates.md 的索引加到 SKILL.md 顶部 "Reference index" 段 (低风险快修, 0.5h), 不动 spec 本身。

## B 不反对方

- candidates.md 本身写得**质量合格** (8 段齐, 10 候选, R-12~16 贯穿, 21KB 信息密度合理)
- 3 个 P0 候选作为**未来 R_{n+1}+ 的参考样本**有价值
- 排除段 (Claude Equity Research 投顾化) 作为**反面对照**有警示价值
**这些都同意, 只是不同意"现在并入 + 改 spec"**。
