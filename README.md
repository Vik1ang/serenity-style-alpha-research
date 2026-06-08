# Serenity-Style Alpha Research

## Reference index

- **A 股总入口** — `skills/serenity-style-alpha-research/references/a-share-skill-spec-FINAL.md`
- **R9 / Biotech BD 收入质量** — `skills/serenity-style-alpha-research/references/a-share-r9-biotech-bd-quality.md`
- **R10 / 大市值剩余重估空间** — `skills/serenity-style-alpha-research/references/a-share-r10-large-cap-rerating-residual.md`
- **完整跑票与复盘样本** — `skills/serenity-style-alpha-research/references/a-share-worked-examples.md`

这是一个面向多 agent 的 Serenity-style alpha research skill / reference 包，可供 Codex、Claude、Gemini 或其他 Markdown-aware agent 使用，用于对上市公司做 chokepoint alpha 研究：
**确定性需求 → 受限供给 → 低关注/误分类 → 价值传导 → 催化 → 反证**。
默认输出语言为中文。

本仓库不是可运行应用，没有构建、测试或服务进程。仓库里的主交付物是 canonical skill 本身：
`skills/serenity-style-alpha-research/`。`.codex/skills/serenity-style-alpha-research/`
只是当前仓库的 Codex project-level 安装镜像；Claude / Gemini / 其他 agent 应从 `skills/` 读取 canonical 文件。

## 仓库结构

```text
.
├── skills/
│   └── serenity-style-alpha-research/    # canonical，可读/可分发的 skill 包
│       ├── SKILL.md                      # skill 入口 + 触发 metadata
│       ├── references/
│       │   ├── output-template.md        # 完整 memo / shortlist 输出模板
│       │   ├── trading-scenario.md       # 交易推演（非投资建议）状态与触发规则
│       │   ├── domain-extensions.md      # AI / 半导体 / 数据中心电力等扩展
│       │   ├── scoring.md                # 弹性测算和因子 checklist
│       │   ├── a-share-skill-spec-FINAL.md
│       │   ├── a-share-skill-spec-draft.md
│       │   ├── a-share-4-pillars-*.md
│       │   ├── a-share-r4-*.md
│       │   ├── a-share-r5-*.md
│       │   ├── a-share-r6-*.md
│       │   ├── a-share-r9-*.md
│       │   └── a-share-r10-*.md
│       └── agents/
│           └── openai.yaml               # UI-facing skill metadata
├── .codex/
│   └── skills/
│       └── serenity-style-alpha-research/ # Codex 本地安装镜像
├── docs/
│   ├── agent-integration.md              # Codex / Claude / Gemini / generic LLM 接入说明
│   ├── a-share-maintenance-backlog.md
│   └── decisions/                        # 维护决策、候选池与 peer-discussion，不进入运行时
├── README.md
├── AGENTS.md                             # OpenAI/Codex-style agent 入口说明
├── CLAUDE.md                             # Claude Code 入口说明
├── GEMINI.md                             # Gemini / Markdown-aware agent 入口说明
└── .gitignore
```

`.omx/` 和 `.claude/` 是本机 agent/harness 状态目录，已通过 `.gitignore` 排除。

## 安装 / 使用

### Codex / OpenAI

把 canonical skill 目录复制到任意 Codex-compatible 环境：

```bash
# 项目级安装
cp -r skills/serenity-style-alpha-research \
      <your-project>/.codex/skills/

# 或用户级安装
cp -r skills/serenity-style-alpha-research \
      ~/.codex/skills/
```

本仓库中，`.codex/skills/serenity-style-alpha-research/` 保持为本地 Codex 加载镜像。
维护时需要让 `skills/serenity-style-alpha-research/` 和 `.codex/skills/...` 同步。

### Claude / Gemini / 其他 agent

- Claude Code：读 `CLAUDE.md`，再按任务加载 `skills/serenity-style-alpha-research/SKILL.md` 和相关 `references/`。
- Gemini CLI / 其他 Markdown-aware agent：读 `GEMINI.md` 或 `AGENTS.md`，再加载 canonical `skills/` 文件。
- 无原生 skill loader 的聊天模型：直接提供 `SKILL.md` + 需要的 reference 文件；A 股任务先给 `a-share-skill-spec-FINAL.md`。
- 跨 agent 维护细节见 `docs/agent-integration.md`。

常见触发语：

- “谁受益？”
- “找类似 Serenity 的机会”
- “帮我筛选”
- “这个逻辑对吗？”
- “验证一个 chokepoint thesis”
- “跑一只 A 股 / 美股候选”

## 这个 skill 产出什么

- **快速 Triage**：单条新闻、公告、推文、市场传闻的快速判断。
- **选股 Shortlist**：longlist → evidence filter → shortlist / watchlist / excluded。
- **完整研究 Memo**：深度研究时使用 `references/output-template.md`。
- **公司核验**：对指定 ticker 先查财务和市场数据，再判断产业链暴露和财务传导。
- **A 股 thesis-level 分桶**：从 `a-share-skill-spec-FINAL.md` 开始，按任务加载 R4/R5/R6，Biotech BD 加载 R9，大市值剩余重估加载 R10。
- **交易推演（非投资建议）**：当用户问“怎么交易/能不能做”时，按 `references/trading-scenario.md` 输出可交易研究对象 / 等待触发 / 仅观察 / 回避交易 / 数据不足，以及触发器、checkpoints、反证和风险控制重点。

结论只使用文本状态和置信度，不使用 A/B/C/D 评级。交易推演只做情景分析，不输出直接买入/卖出/仓位/目标价/止损价建议。

## A 股研究栈

A 股方法论不是美股 Serenity 框架的逐条翻译，而是一套独立栈。

推荐阅读顺序：

1. `references/a-share-skill-spec-FINAL.md` — 最终总览和文件索引。
2. `references/a-share-skill-spec-draft.md` — D3 工作草稿和 R4-R6 索引。
3. `references/a-share-r4-thesis-bucketing-announcement-calibration.md` — thesis-level 分桶、公告反证 6 级、媒体订单规则。
4. `references/a-share-r5-ma-target-layering-smallcap-redflags.md` — 并购/新设业务载体分层、公司级财务/治理红旗。
5. `references/a-share-r6-market-structure-minimum-evidence.md` — R2/R3 市场结构证据、市值数据日期、大票/小票风险定价差异。
6. `references/a-share-r9-biotech-bd-quality.md` — Biotech BD 收入质量专项。
7. `references/a-share-r10-large-cap-rerating-residual.md` — 大市值剩余重估专项。
8. `a-share-4-pillars-*.md` — R1 来源、review 和 peer discussion，只在方法论 review 时加载。

完整案例与复盘统一放在 `references/a-share-worked-examples.md`；专项规则的额外验证样本记录在对应 R9/R10 文档。

## 数据纪律

证据权重从高到低：

1. **Primary**：财报、交易所公告、公司公告、电话会/投资者关系记录。
2. **Cross-check**：客户、供应商、竞争对手、行业数据。
3. **Market data**：价格、市值、流动性、估值、short interest/options 等。
4. **Secondary**：可信媒体、券商摘要；只能作线索，不替代原始证据。
5. **Social media**：只能作为 thesis input，不能单独支撑强结论。

对具体公司做判断时，能查就查最新财务和市场数据。关键证据缺失时，只能放入
`Watchlist / 待核验` 或 `Excluded / 剔除`，不能硬凑强 Alpha 结论。

## 维护规则

- `skills/serenity-style-alpha-research/SKILL.md` 是 canonical skill 入口，frontmatter 不能删。
- `.codex/skills/serenity-style-alpha-research/` 是本地 Codex 镜像；维护时必须与 `skills/` 同步。
- `AGENTS.md` / `CLAUDE.md` / `GEMINI.md` 是 agent adapter 文档；行为边界变化时要一起更新。
- 运行时方法论放在 `references/`；候选池、行动计划和辩论记录放在 `docs/decisions/`，不得加入运行时加载路径。
- A 股方法论改动遵循 ownership：
  - D3：总览 / 索引。
  - R4：thesis-level 分桶与公告反证。
  - R5：业务载体分层与公司级财务/治理红旗。
  - R6：市场结构证据与 R2/R3 风险定价。
  - R9：Biotech BD 收入质量。
  - R10：大市值剩余重估与 price-in。
  - D4 FINAL：顶层阅读路径变化时更新。
- 不新增 A/B/C/D rating；不输出直接买入/卖出/仓位/目标价/止损价建议。
- 允许输出“交易推演（非投资建议）”：按 `references/trading-scenario.md` 只写状态、触发器、checkpoints、反证条件和风险控制重点。

## 待办 / 维护 backlog

A 股后续维护项写在：`docs/a-share-maintenance-backlog.md`。
外部 benchmark、候选池和 peer-discussion 归档在：`docs/decisions/competitive-benchmark-2026-06-08/`。

当前主要待办：

- 新增 A 股固定输出模板 `references/a-share-output-template.md`。
- 建公告反证 6 级样本库。
- 未来考虑 R5 文件名重命名 / redirect。
- 未来考虑拆分大型 R1 provenance 文件。

## License

当前未附 license。公开分发前应补 license 文件。
