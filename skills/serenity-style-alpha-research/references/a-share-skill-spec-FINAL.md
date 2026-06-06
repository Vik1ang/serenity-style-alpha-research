# A 股 Serenity-style Alpha Skill Spec FINAL

## 1. 一页纸总览

这份 FINAL 是 A 股 serenity-style-alpha skill 的总入口，面向第一次接触该体系的人。它不再把美股 gate 逐条翻译到 A 股，而是把 c 路径和 R4-R6 的成果收束成一条可执行研究链：先用 c 路径确认 A 股需要独立方法论，核心是政策/周期前置、倒序信息传播、重估触发路径和涨跌停风险定价；再用三条硬化规则处理冲突优先级、fallback checkpoint 和 materiality 硬门槛；随后用春秋电子倒推补上公告反证、收购/并表、公司入口、缺数据和 Early Optionality 等漏洞。R4 解决输出单位和公告反证校准，R5 解决并购标的分层和小票财务红旗，R6 解决市场结构数据最低证据标准。实际跑票时，默认按 thesis-level 分桶，公司级只做 summary；风险、公告反证和财务硬门槛优先于题材叙事。 本 FINAL 已整合 4 步轻改：R4 加媒体订单规则 / R5 扩展新设业务载体 + 加红旗量化阈值 / R6 加市值档位数据日期。

## 2. c 路径 3 步

c 路径底稿见 `a-share-4-pillars-spec.md`，外部 review 见 `a-share-4-pillars-spec-hermes-review.md`，收敛规则见 `a-share-4-pillars-peer-discussion-r1.md`。这三份文件定义 A 股 skill 的方法论骨架、review 问题和三条硬化规则。 该 review 只覆盖 R1，不覆盖 R4-R6 后续规则。

## 3. R4 8.1 + 8.3

R4 详见 `a-share-r4-thesis-bucketing-announcement-calibration.md`。它处理两个强耦合问题：默认按 thesis-level 分桶，以及公告反证 6 级如何作用到具体 thesis，而不是粗暴作用到公司整体。 R4 包含 8.1 thesis-level 分桶 + 8.3 公告反证 6 级 + 媒体订单不能作 confirmation 规则。

## 4. R5 8.2 + 8.5

R5 详见 `a-share-r5-ma-target-layering-smallcap-redflags.md`。它把收购标的拆成现有主营、目标新业务、停摆业务和重启路径，并把质押、商誉、ST/退市、再融资、应收存货和业绩预亏纳入公司级风险覆盖层。 R5 包含 8.2 并购/新设业务载体分层 + 8.5 公司级财务/治理红旗量化触发线（9 阈值）。

## 5. R6 8.4

R6 详见 `a-share-r6-market-structure-minimum-evidence.md`。它定义 R2/R3 的最低数据包、缺数据时的 R2 / 数据不足处理、公司级与 thesis-level 市场结构信号的映射，以及数据源优先级。 R6 包含 8.4 市场结构数据最低证据 + R6 §3 Large-cap crowding vs Small-cap relay + 市值档位数据日期强制要求。 R9 见 `a-share-r9-biotech-bd-quality.md`（Biotech BD 收入质量 gate）。

## 6. 跑票流程

跑票流程引用 `a-share-skill-spec-draft.md` 第 6 段：政策→倒序→重估→涨跌停。先判断产业背景和公司入口，再判断传播阶段，再检查 background/catalyst/confirmation，最后用 R2/R3 市场结构处理价格风险。

## 7. 春秋电子 worked example

春秋电子示例引用 `a-share-skill-spec-draft.md` 第 7 段。该例证明同一家公司必须拆 thesis：AI PC 和机器人因公告反证进入 Excluded，数据中心液冷 / Asetek 因缺并表收入、客户订单和合同金额+时间保留 Watchlist — Early Optionality。

## 8. 三桶分桶 + reconcile

三桶规则引用 `a-share-skill-spec-draft.md` 第 5 段，并结合 R4/R5：Shortlist 是确认型基本面候选，Watchlist — Early Optionality 是早期可选性待核验，Excluded 是反证或风险压倒；公司级红旗可覆盖全部 thesis。 R4-R6 worked examples 见 `a-share-worked-examples.md`（3 案例：春秋/鹏鼎/黄河 + 2 占位：赛力斯/百利天恒）。
