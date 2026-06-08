# candidates-2026-06-08 双盲辩论矩阵 (2026-06-08) — 第 2 轮修订

> 来源:
> - A 立场: `candidates-debate-side-a-codex.md` (3,661 bytes, 8 条)
> - A 对 B 回应: `candidates-debate-codex-response.md` (4,982 bytes, 8 条)
> - B 立场: `candidates-debate-side-b-hermes.md` (4,827 bytes, 8 条)
> - B 对 A 回应: `candidates-debate-hermes-response.md` (8 条)
> - 候选池: `candidates-2026-06-08.md` (21,871 bytes, 10 候选)
> - 既有 action plan: `competitive-benchmark-action-plan.md` (未改, 9 项 + 5 风险)
>
> 3-step peer-discussion: A 写立场 / B 写立场 / 双方写交叉回应 / 收敛矩阵
>
> 产物: 5 件套 (A 立场 + A 对 B + B 立场 + B 对 A + 本矩阵), 全部并存不覆盖
>
> 矩阵只**引用** A 对 B 跟 B 对 A 的回应立场, 不重写全文, 避免变成"我拍"

## 矩阵 (A 8 条 vs B 8 条, 第 2 轮)

| # | A 立场 | B 立场 | A 对 B 回应 | B 对 A 回应 | 终判 (Vik1ang 拍) | 落点 |
|---|---|---|---|---|---|---|
| 1 | **A-1** 修 P0-1 索引漂移 | **B-1** candidates 跟 action plan 同源, 不产生新执行项 | **disagree** "并入 ≠ 不增新执行项" | **agree** 跟 A-1 收敛, 修索引都同意 | **AGREE 完全** | **R_n 本周**: P0-1 修 SKILL/FINAL/README 索引 |
| 2 | **A-2** Registry 是 P0-2 证据升级 (Thesis OS) | **B-2** 3 个 P0 新候选是"对应"不是"新增" | **agree** (主动修订) "不再叫新增 P0" | **agree 部分** (修订) "加 1 段 ## 外部参考, 跑稳后补" | **AGREE 完全** (修订后) | **R_n 本月**: P0-2/3/4 共同设计, **不引 candidates** |
| 3 | **A-3** Citation + Data Status 最小发布门禁 | **B-3** AlphaAnalyst/XVARY 是重型应用, 不照搬 | **agree** "不照搬, 只吸收可观察语义" | **agree 部分** (修订) "不引具体 repo URL" | **AGREE 完全** (修订后) | **R_n 本月**: 落最小门禁, 不引 URL |
| 4 | **A-4** 口径漂移登记 R_{n+1}+, 不塞 R5 | **B-4** R-12 已经在 action plan 第 160 行 | **needs-discussion** "R-12 是否机器可读" | **needs-discussion** (趋 agree) "本周 P0-1 顺手核对" | **AGREE 完全** (修订后) | **R_n 本周** (P0-1 范围): 核对 R-12~16 是否已 SKILL 顶层覆盖 |
| 5 | **A-5** 跨市场空白真实, 不本月实现 | **B-6** 港股/美股/加密空白是设计选择 | **needs-discussion** "Registry 预留 market/asset_type/materiality 字段" | **needs-discussion** (趋 agree) "用 A-5 形式 + B-6 哲学" | **AGREE 完全** (修订后) | **R_n 本月**: Registry 预留字段, 不实现 adapters |
| 6 | **A-6** 合并成本 < 维持两份并行真相 | **B-7** action plan 9 → 15 项 = 决策变难 | **disagree** "action plan 加证据列不减项" | **disagree** (但妥协) "不并入, 加 SKILL.md 顶部 1 行索引" | **NEEDS-DISCUSSION 收敛** | **不并入**, **加 SKILL.md 顶部 1 行索引** (0 成本, 改天 1 季再评估) |
| 7 | **A-7** 风险约束 R-12~16 写成验收条件 | **B-4** 强化 R-12 应在 SKILL.md 顶层 | **needs-discussion** "核对 R-12 是否已可执行" | **needs-discussion** (趋 agree) "核对后不加新段" | **AGREE 完全** (修订后) | **R_n 本周** (P0-1 范围): 核对 R-12 是否已覆盖 |
| 8 | **A-8** 计划现在合并, 实施按两种速度 | **B-8** 辩论触发条件是"执行时遇新坑" | **disagree** "等已知失败再发生不是更稳" | **needs-discussion** (但有收敛) "本周 P0-1 + 本月 P0-2/3/4 + 季度后评估" | **AGREE 完全** (时机收敛) | **R_n**: 本周 + 本月; **R_{n+1}+**: 4 项登记 + 季度后评估 |

## 收敛: R_n (本周/本月) vs R_{n+1}+ (季度后)

### R_n 本周 (1 项, 2-3h, low risk)
- **P0-1 修索引漂移**: SKILL.md:209-223 + FINAL.md + README/CLAUDE/GEMINI 加 R9/R10 入口
- **副作用 1**: 顶部 "Reference index" 段加 1 行 candidates.md (缓解 A-6 vs B-7 矛盾)
- **副作用 2**: 顺手核对 R-12~16 是否已被 SKILL 顶层"硬约束" 段覆盖, 覆盖则不动

### R_n 本月 (1 项, 1-2 周, 中风险)
- **P0-2/3/4 共同设计**: 落 Registry schema (容纳 citation tier + 6 数据状态)
- **加 1 项**: Registry 预留 market + asset_type + 独立 materiality 字段 (跨市场接口, 暂不实现)
- **不引**: candidates.md 来源 + AlphaAnalyst/Thesis OS/XVARY URL (避免 R-15 文档漂移)
- **跑稳后补**: 1 季后加 1 段 "## 外部参考" 引用 3 个 P0 候选

### R_{n+1}+ 季度后 (4 项, 等 P0-1 + P0-2/3/4 跑稳)
1. **Comparability gate**: 口径漂移 (KPI/分部重组/非 GAAP) 检测 — 跑票 1-2 个遇到案例时登记 owner
2. **跨市场 adapters**: 港股/美股/日股/crypto adapters — 真实任务触发时
3. **物理拆包决策** (P2-6): discovery/research/monitoring/review 4 sibling skills — P0-2 Registry + P1-5 cron 跑稳后
4. **candidates 是否并入 action plan**: 1 季后跑稳 P0 + 1-2 轮 R11, 评估 10 候选哪些真用到

## 跟 R-12~16 风险约束的兼容性检查

- ✅ **R-12** (不学 ZhuLinsen 买卖信号): A-7 + B-4 + Codex B-4 回应都同意, 不动
- ✅ **R-13** (不照抄 24-skill 粒度): A-5 + Codex A-5 回应同意
- ✅ **R-14** (不削弱现有强项): A-4 (R5 不动) + A-7 (R4-R10 不覆盖) 同意
- ✅ **R-15** (警惕外部文档漂移): **A-6 vs B-7 矛盾**, **R_n 决定 = candidates 不并入 + SKILL.md 顶部 1 行** 缓解
- ✅ **R-16** (Registry 比 cron 更重要): P0-2 优先于 P1-5 cron, 同意

## 关键矛盾点 (第 2 轮后收敛)

### 矛盾 1: candidates.md 是否并入 action plan
- A-6 立场: 并 (合并成本 < 双真相)
- B-7 立场: 不并 (15 项难决策)
- Codex A 对 B 回应 (B-7): "action plan 加证据列不减项"
- Hermes B 对 A 回应 (A-6): "不并, 加 SKILL.md 顶部 1 行索引"
- **终判 (收敛)**: **不并入 action plan**, 但 **SKILL.md 顶部 "Reference index" 段加 1 行 candidates.md**。 等季度后回头评估。
- **理由**: P0-1 修索引漂移本身就要加 "Reference index" 段, 顺带加 candidates.md 是 0 成本。 但 action plan 是 9 项决策清单, 加候选会让"决策清单"和"参考池"混淆。

### 矛盾 2: P0-2/3/4 共同设计是否引用 candidates 来源
- A-2/A-3 立场: 引 (外部验证样本)
- B-2/B-3 立场: 不引 (避免双真相膨胀)
- Codex A 对 B 回应 (B-2/B-3): 主动修订, "不再叫新增 P0"
- Hermes B 对 A 回应 (A-2/A-3): "加 1 段 ## 外部参考, 跑稳后补"
- **终判 (收敛)**: **不引, 改天跑稳后补**
- **理由**: 共同设计时 schema 一次定, 跑稳后加 1 段 "## 外部参考" 引用 3 个 P0 候选, 不在设计期污染。

### 矛盾 3: 跨市场是不是 urgent
- A-5 立场: 真实空白, 但不本月实现
- B-6 立场: 设计选择不是缺口
- Codex A 对 B 回应 (B-6): "Registry 预留 market/asset_type/materiality 字段"
- Hermes B 对 A 回应 (A-5): "用 A-5 形式 + B-6 哲学"
- **终判 (收敛)**: **A-5 形式 (Registry 预留字段) + B-6 哲学 (不实现, 等真实任务)**
- **理由**: A-5 给出了具体落地形式, B-6 哲学保留。 Registry 预留字段是 0 成本低风险快修, 等真实任务再决定实现。

## Vik1ang 拍板选项

| 选项 | 含义 | 工作量 | 风险 |
|---|---|---|---|
| **1 推** | R_n 本周 (P0-1 + 副作用 2 项) + R_n 本月 (P0-2/3/4 + Registry 字段) + R_{n+1}+ 4 项登记 | 1-2 周 (跟 R10 节奏) | 低-中 |
| **2 alt** | R_n 减半: 只 P0-1 本周, P0-2/3/4 推迟 1 月 | 本周 1 项 | 低 |
| **3 不推** | 暂停, 候选池当 reference 1 季, R11 跑票遇新坑再回头 | 0 本周 | 0 (但失去 P0-1 快修窗口) |

**Hermes 推 1**——理由:
- P0-1 是 low-risk 快修 (2-3h), 副作用 (1 行索引 + R-12 核对) 各 0.5h
- P0-2/3/4 共同设计是 R10 收口后**自然下一步**, Registry 预留字段是 0 成本
- candidates 池不并入 action plan, 只加 SKILL.md 顶部 1 行 (R-15 缓解)
- 1 季后回头评估 candidates 是否真用到 (B-8 时机哲学保留)

## 5 件套 (本轮交付)

| 文件 | 作者 | 字节 | 段数 |
|---|---|---|---|
| `candidates-debate-side-a-codex.md` | Codex | 3,661 | 8 立场 |
| `candidates-debate-codex-response.md` | Codex | 4,982 | 8 回应 |
| `candidates-debate-side-b-hermes.md` | Hermes | 4,827 | 8 立场 |
| `candidates-debate-hermes-response.md` | Hermes | ~5,200 | 8 回应 |
| `candidates-debate-2026-06-08.md` (本文件) | Hermes | ~9,500 | 7 段矩阵 |
| `candidates-2026-06-08.md` | Codex | 21,871 | 8 段 (10 候选) |

**Verify**: R4/R5/R6/R9/R10 + SKILL.md + FINAL.md + action plan SHA 全部未变。
