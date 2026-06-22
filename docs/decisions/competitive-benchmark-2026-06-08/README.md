# Competitive Benchmark Decision Archive — 2026-06-08

这组文件记录外部 skill 横向对照、候选池和双盲 peer discussion。它们是**维护决策与 provenance**，不是运行时研究规则，agent 执行股票研究时不应加载。

## 文件职责

- `competitive-benchmark-action-plan.md` — canonical 改进 backlog；P0-1 已完成，其余项目仍需单独授权和验证。
- `candidates-2026-06-08.md` — 外部候选与证据池，不直接生成 structural alpha 功能。
- `candidates-debate-2026-06-08.md` — 双盲辩论收敛矩阵。
- `candidates-debate-side-a-codex.md` / `candidates-debate-side-b-hermes.md` — 双方初始立场。
- `candidates-debate-codex-response.md` / `candidates-debate-hermes-response.md` — 双方交叉回应。

## 当前边界

- 运行时入口只读取 `skills/structural-alpha-research/SKILL.md` 和任务所需 references。
- 本目录不复制到 `.codex/skills/`，避免维护材料进入模型常规上下文。
- Candidate Registry、citation contract、block-level data status 和 cron 尚未实现；需要时从 action plan 单独立项。
