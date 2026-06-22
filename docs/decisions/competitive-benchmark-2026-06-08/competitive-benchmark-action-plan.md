# structural alpha 改进行动清单 (2026-06-07)

> 来源: 横向对照 4 个 GitHub 同类 repo (spikeHongg / belos-street / yanglaiyang / ZhuLinsen) + Codex A 轮逐条表态 + Hermes 验证 + Hermes 修正。
>
> 目的: 把"研究外部 skill"的结论,转成 structural alpha 自己的"可执行改进清单"。**不写代码,只列计划**。改天照单改。
>
> 状态（2026-06-08）：P0-1 索引修复已完成；P0-2/3/4、cron 和其他候选均未实施。

## 总体判断

**值得学** vs **不值得学**:
- 值得学 9 项 (P0: 4 / P1: 3 / P2: 3)
- 不入清单 1 项 (P2-11 yanglaiyang 可视化)
- 风险保留 5 项 + 1 项升级为实施依赖约束 (R-16)

**Codex A 轮关键修正** (写进所有 P0 设计的隐含约束):
1. **P0-2/3/4 共同设计** —— Registry schema 必须同时容纳 citation + block-level data status, 不能拆开做
2. **P1-8 不抄 spikeHongg** —— structural alpha 自己的 6 模式: 多 thesis / 并购载体 / Biotech BD / 大市值重估 / 题材接力 / 普通 chokepoint
3. **P1-6 拆 4 skills 暂不做** —— 先用 references 定义接口, 跑 1 季再决定物理拆包
4. **P2-11 可视化暂不入清单** —— 数据闭环未建立, 图表会伪精确

---

## 改进行动清单 (9 项)

### P0 (4 项) — 本周/本月必做

#### P0-1 修复主 SKILL / FINAL 索引漂移

| 字段 | 内容 |
|---|---|
| **来源** | 自有 (Codex 第二阶段盲点 + R-15 漂移风险) |
| **改什么** | `skills/structural-alpha-research/SKILL.md` §"Stock-Picking Workflow" + `skills/structural-alpha-research/references/a-share-skill-spec-FINAL.md` §"入口" + 同步更新 `.codex/skills/...` 镜像 + README / CLAUDE / GEMINI |
| **改前问题** | R9 / R10 已成型有效模块, 但主入口 209-223 行 + FINAL.md 没完整路由, agent 加载时可能跳过 R9/R10 → 模型根本不加载有效规则 |
| **改后方案** | 主 SKILL.md 的 "Stock-Picking Workflow" 增加 R9 / R10 显式分支; FINAL.md 顶部加 "活跃 references 索引" 表 (R4-R10 + worked-examples), 每份 references 一行 |
| **工作量** | 2-3 小时 |
| **依赖** | 无 (低风险快修) |
| **风险** | 改错路径会断链 → 镜像目录 `.codex/skills/...` 同步后做 `grep -r "R9\|R10"` verify |

#### P0-2 Candidate Registry & Lifecycle Spec

| 字段 | 内容 |
|---|---|
| **来源** | 自有 (Codex 第二阶段收敛: "如果只做 1 件事") |
| **改什么** | **新增** `skills/structural-alpha-research/references/a-share-r11-candidate-registry-lifecycle.md` (论文级, 6 块: thesis_id 规则 / 状态机 / 证据截止日 / checkpoint / 复盘 / 跟 R4-R10 引用) |
| **改前问题** | 跑过的 case 都"扔了" — 春秋 / 鹏鼎 / 黄河 / 赛力斯 / 百利天恒 都没沉淀; cron / 复盘 / 案例库无可靠锚点 |
| **改后方案** | 每个 thesis 有 thesis_id (股票代码 + thesis 类型 + version 序号, 例 `002281-R1.6T-v003`) / 状态机 5 档 / 证据截止日 / checkpoint 复查周期 / 复盘 4 类标签 (前瞻/事后/反例/边界) |
| **工作量** | 4-6 小时 (含 Hermes 独立 verify) |
| **依赖** | 必须同时容纳 P0-3 (citation) + P0-4 (数据状态) — **共同设计, 不能拆开做** |
| **风险** | 字段定错后期难改 → 先写最小 schema 跑 5-10 个 case 验证, 再扩 |

#### P0-3 Citation 一等公民 (收窄版)

| 字段 | 内容 |
|---|---|
| **来源** | spikeHongg (citation-standard 48 行) |
| **改什么** | **新增** `skills/structural-alpha-research/references/citation-standard.md` (收窄版, 不照搬 spikeHongg); `SKILL.md` "Data Discipline" 段加引用硬规则 |
| **改前问题** | 现在 spec 没强制引用, agent 容易凭印象跑 |
| **改后方案** | **强制引用 6 类**: ① 决定分桶的事实 ② 硬阈值触发 ③ 财务数字 ④ 公告反证 ⑤ 关键市场数据 ⑥ 表格关键行。一般背景叙述允许段落级引用。3-tier 证据 (Tier 1 法定 / Tier 2 部委 / Tier 3 公司媒体) |
| **工作量** | 3-4 小时 |
| **依赖** | 与 P0-2 共同设计 — Registry 内每个证据要带 citation tier + URL |
| **风险** | 引用过重 → 长报告难读 → 明确"段落级引用"豁免一般背景 |

#### P0-4 Block-level 数据状态契约 (升 P0)

| 字段 | 内容 |
|---|---|
| **来源** | ZhuLinsen (AnalysisContextPack 6 状态) + Hermes 验证词频 |
| **改什么** | **新增** `skills/structural-alpha-research/references/data-status-contract.md` + `trading-scenario.md` "Required Inputs" 段 (~11-23 行) 加状态字段; `SKILL.md` "Data Discipline" 段加契约 |
| **改前问题** | R10 三案例 (赛力斯 / 长电 / 茅台) 全部数据不足, 整篇报告只标一次"数据不足"不够精确 — 5 项数据经常缺 1-2 项, 不能粗判 |
| **改后方案** | 6 状态: `available` / `missing` / `stale` / `fallback` / `estimated` / `partial` (外加 `fetch_failed`)。每个证据块自带状态, 不只整篇标 1 次 |
| **工作量** | 4-6 小时 |
| **依赖** | 与 P0-2 共同设计 — Registry 内每证据带 status 字段 |
| **风险** | 状态定义不一致 → 6 状态 + 边界规则写在 spec 顶部, agent 必须先读 |

---

### P1 (3 项) — 月内可做

#### P1-5 + P1-7 cron 研究队列仪表盘 + 通知去重 (合并)

| 字段 | 内容 |
|---|---|
| **来源** | ZhuLinsen (GitHub Actions / 报告模板 / 多渠道通知) |
| **改什么** | **新增** `skills/structural-alpha-research/references/discovery-monitoring-pipeline.md` + `.github/workflows/structural alpha-research-digest.yml`; `SKILL.md` "Response Depth" 加 "定期候选扫描/跟踪摘要" 模式; `output-template.md` 加 "状态变化摘要" |
| **改前问题** | 现在没有 cron, agent 跑完就忘, 长期挖股无闭环 |
| **改后方案** | 定时输出 7 类: 新增候选 / 状态变化 / 新证据 / 证据过期 / checkpoint 到期 / 风险红旗 / 下一步研究优先级。**不输出**买卖 / 仓位 / 点位。通知去重: `company + thesis_id + event_type` 去重, 严重度按分桶变化 / 强反证 / 红旗 / checkpoint 分级 |
| **工作量** | 3-5 天 (单一数据源 + Discord MVP) |
| **依赖** | **P0-2 / P0-3 / P0-4 必须完成且跑稳** (R-16 实施依赖约束); 否则定时生成重复候选和低质量提醒 |
| **风险** | 推送噪音 → 严重度分级 + 冷却 + quiet hours; 数据源挂 → 6 状态里 `fetch_failed` 显式标 |

#### P1-8 structural alpha 自定义 routing 矩阵 (6 模式, 不抄 spikeHongg)

| 字段 | 内容 |
|---|---|
| **来源** | spikeHongg routing-matrix (7 pattern) 借鉴**结构**; structural alpha 自己的 5 因子 + 5 桶 |
| **改什么** | **新增** `skills/structural-alpha-research/references/routing-matrix.md` (6 模式) + `SKILL.md` "Stock-Picking Workflow" 段引用 |
| **改前问题** | 现在跑票靠 agent 临时判断, 模式不显式; 同 thesis type 跑法应一致 |
| **改后方案** | 6 模式自定义: ① 多 thesis ② 并购载体 ③ Biotech BD ④ 大市值重估 ⑤ 题材接力 ⑥ 普通 chokepoint。每模式 → 必跑 R-series 子集 + 可选子集 + ordering rule |
| **工作量** | 1-2 天 |
| **依赖** | 无 (但 R9/R10 已有的 Biotech BD / 大市值重估模式可直接复用) |
| **风险** | 模式分错 → 跑 5-10 个 case 验证, 错则并入/拆出 |

---

### P2 (3 项) — 季度内可做

#### P2-6 是否拆 4 个 sibling skills (decision-only)

| 字段 | 内容 |
|---|---|
| **来源** | belos-street (24-skill 模块化, 但不照抄) + spikeHongg (母 skill + 子模块结构) |
| **改什么** | **不拆**, 只决策。`SKILL.md` 加 1 段 "Future Decomposition Decision" 说明: 跑稳 1 季后, 视情况拆 discovery/research/monitoring/review 四个 sibling skill |
| **改前问题** | 现在拆包会破坏 R4-R10 单一入口的一致性 (R-13 + Codex 第二阶段盲点) |
| **改后方案** | 先用 references 定义接口, 跑 1 季再决定物理拆包; 拆包不复制 belos 24-skill 粒度 |
| **工作量** | 0.5 小时 (只写决策段) |
| **依赖** | P0-2 Registry 跑稳 + P1-5 cron 跑 1 季 |
| **风险** | 拆后路由冲突 → 拆前先在 references 层定义接口和触发条件 |

#### P2-9 Discovery prior 隔离 (只决定"先研究谁")

| 字段 | 内容 |
|---|---|
| **来源** | belos-street (investment-idea-generator: 量化筛选 / 主题扫描 / 事件扫描分开) |
| **改什么** | `skills/structural-alpha-research/references/scoring.md` 拆"发现分"和"研究置信度"两块; **新增** `skills/structural-alpha-research/references/discovery-signals.md` |
| **改前问题** | discovery 信号容易污染 Shortlist 置信度, 引入题材热度偏差 |
| **改后方案** | discovery 信号 (主题 / 订单 / 预期差 / 估值 / 质量 / 特殊事件) → 只决定"先研究谁" (进 Longlist), **不能**提高 thesis 置信度或直接进 Shortlist; Shortlist 仍必须经过 demand/bottleneck/materiality/R4-R10 完整证据链 |
| **工作量** | 1-2 天 |
| **依赖** | 无 |
| **风险** | discovery score 跟 Shortlist 混用 → 写 spec 时显式隔离, agent 必须读完 discovery-signals.md 才能跑 |

#### P2-10 一页纸稳定 Markdown 产物

| 字段 | 内容 |
|---|---|
| **来源** | yanglaiyang (七步简化分析) + 借鉴其"稳定产物"思路 |
| **改什么** | `skills/structural-alpha-research/references/output-template.md` "Compact Formats" 后新增 "One-page Investment Research Record"; 复用 P0-2 Registry 字段 (不另建状态体系) |
| **改前问题** | 现有 Compact Format 更像即时回答, 不是可长期回填的决策记录 |
| **改后方案** | 每页固定包含: thesis / 关键事实 / 反证 / 状态变化 / checkpoint / 证据截止日 / 来源。Markdown 优先, 可 diff / 可季度回填; **不做 HTML / 可视化** |
| **工作量** | 4-6 小时 |
| **依赖** | P0-2 Registry 字段定下后 |
| **风险** | 跟现有 output-template 重复 → 明确"一页纸 = 决策记录"vs "现有模板 = 完整研究输出"两种产物 |

---

## 不入清单 (1 项)

### P2-11 yanglaiyang src/analysis_prompts/ 9 模块 + 可视化报告

**不入理由** (Codex A 轮 Disagree + 收口):
- structural alpha 现在缺**数据闭环**, 不是图表
- 雷达图容易把不同证据质量压成**伪精确分数**
- 热图和瀑布图只有在存在**稳定结构化时间序列**后才有意义
- 未来若需要展示层, 再单独评估

---

## 风险约束 (5 条保留, 1 条升级)

| # | 风险 | 等级 | 落地方式 |
|---|---|---|---|
| R-12 | 不学 ZhuLinsen 买卖信号 | 硬约束 | structural alpha 输出层 hard rule: 永远只出 5 档非建议状态 |
| R-13 | 不照抄 24-skill 粒度 | 硬约束 | P2-6 决策段 + 拆包前必须用 references 接口验证 |
| R-14 | 不削弱现有强项 | 硬约束 | 任何改进只能**包裹** thesis-level / 公告反证 / 公司级红旗, 不能替换 |
| R-15 | 警惕外部文档漂移 | 软约束 | 每新增 reference 必做: 入口索引 + 链接检查 + 职责 owner |
| R-16 | **Registry 比 cron 更重要** | **实施依赖约束** (升级) | **P1-5 cron 启动前置条件 = P0-2/3/4 跑稳**; 允许手工一次性扫描验证候选来源, 但不建设持续推送管线 |

---

## 本周 1 项 + 本月 3 项 (Codex C 轮未跑, Hermes 提议)

> Codex C 轮未跑 (你 A 轮后直接消化)。这里由 Hermes 按 A 轮表态 + 风险约束拍。

### 本周 1 项: **P0-1 修索引漂移**

理由:
- **低风险快修** (2-3h), 本周可完成
- **无前置依赖** — 不需要 Registry / Citation / 数据状态跑稳
- **清掉信息架构债** — 让后续所有 P0 改进有稳定入口
- **风险已明** — 镜像同步 + grep verify, 改错可秒回滚

### 本月 3 项: P0-1 + P0-2 + P0-4

理由:
- **P0-1 单独跑 (本周)** — 不需要共同设计
- **P0-2 + P0-4 共同设计 (1-2 周)** — Codex 修正明确要求: Registry schema 必须同时容纳 citation + block-level data status, 不能拆开做
- **P0-3 Citation 推到下月** — 等 P0-2/4 schema 定下后, citation 字段直接嵌入 (避免重复改 schema)

**本月明确不动的** (按 R-12~16):
- 不学 ZhuLinsen 买卖/仓位/点位 (R-12)
- 不抄 belos-street 24-skill 粒度 (R-13)
- 不削弱 thesis-level / 公告反证 / 公司级红旗 / 数据不足纪律 (R-14)

---

## 验证清单 (改天后照单 verify)

- [ ] P0-1: `grep -r "R9\|R10" skills/ references/` 全部有引用
- [ ] P0-1: `.codex/skills/...` 镜像与 canonical 同步
- [ ] P0-2: thesis_id 格式 `XXX-ThesisType-vN` 在 5-10 个 case 上跑通
- [ ] P0-3: 6 类强制引用 + 3-tier 证据全文档贯穿
- [ ] P0-4: 6 状态 + `fetch_failed` 在 R10 三个 case 上重跑, 每个证据带状态
- [ ] P0-2/3/4 共同设计: schema 一次定, 不返工
- [ ] P1-5: 严重度分级 + 冷却 + quiet hours 验证
- [ ] P1-8: 6 模式在 5-10 个 case 上跑通, 模式分配合理
- [ ] R-16: cron 启动前 P0-2/3/4 跑稳
