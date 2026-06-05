# A 股 R4 Spec — Thesis-level 分桶与公告反证校准

R4 聚焦两个强耦合问题：默认按 thesis 分桶，并把公告反证 6 级校准到具体 thesis 上。

## 8.1 公司级分桶 vs thesis-level 分桶

### 1. 默认输出单位是 thesis，不是公司

A 股小票经常同时挂多个题材，默认输出单位必须是 **thesis**。公司只是承载多个 thesis 的容器。

最小 thesis 单位：

> 公司 × 业务入口 × 客户/应用场景 × 时间窗口 × 证据状态

例如：

- 春秋电子 × AIPC 终端 × AI PC 消费电子 × 2026 年内 × 公司否认；
- 春秋电子 × Asetek 液冷 × 数据中心客户 × 未来 12-24 个月 × 缺合同/并表；
- 春秋电子 × 机器人 × 机器人整机/零部件 × 2026 年内 × 公司否认。

公司级结论只能是这些 thesis 的汇总，不能替代 thesis-level 判断。

### 2. 多 thesis 怎么分桶

#### 同一公司多 thesis

逐条 thesis 单独分桶：

- 被公告强反证的 thesis → Excluded；
- 有业务入口但缺 confirmation → Watchlist — Early Optionality；
- 有 demand / bottleneck / materiality / confirmation → Shortlist；
- 不允许用一个 Watchlist thesis 稀释另一个 Excluded thesis。

#### 同一 thesis 跨公司

可以建立 thesis cluster，但每家公司仍单独分桶。

例如：

> 数据中心液冷 × A 股供应链 × 2026-2027

下面可以有多家公司，但每家公司必须独立验证：

- 是否真有液冷产品；
- 是否面对数据中心客户；
- 是否有订单/合同/收入；
- 是否达到 materiality。

不能因为行业 thesis 成立，就自动让所有公司进入同一桶。

#### 同一公司跨周期

不同周期必须拆版本。

例如：

- 2025: 收购完成 thesis；
- 2026H1: 并表收入 thesis；
- 2026H2: 数据中心订单 thesis。

每个周期有独立 checkpoint。旧 thesis 未完成，不能自动滚入新周期。

#### 同一 thesis 跨版本

每次新增公告、财报、订单、监管问询、异动公告，都形成 thesis version。

格式建议：

> Thesis v1 / v2 / v3：触发日期 + 新证据 + 分桶变化

这样可以追踪是“thesis 被验证”，还是“市场叙事换壳”。

### 3. thesis 怎么命名

推荐格式：

> [公司] / [业务入口] → [客户群或应用场景] / [时间窗口] / [当前证据状态]

命名必须包含 4 个要素：

1. **业务入口**：公司到底靠什么进入这条链；
2. **客户群或应用场景**：卖给谁，用在哪；
3. **时间窗口**：未来一个季度、12 个月、24 个月；
4. **证据状态**：已收入、已订单、已合同、已并表、待验证、被否认。

例子：

- 春秋电子 / Asetek 液冷 → 数据中心客户 / 12-24 个月 / 待合同与并表；
- 鹏鼎控股 / 光模块 PCB → AI 光模块客户 / 2026 全年 / 已披露低占比；
- 黄河旋风 / 金刚石材料 → AI 散热应用 / 12 个月 / 待客户与收入验证。

不要用：

- “AI 概念”；
- “机器人概念”；
- “液冷概念”；
- “国产替代受益”。

这些不是 thesis，只是标签。

### 4. thesis-level 分桶跟公司级分桶怎么 reconcile

公司级输出只做 summary，不做主判断。

推荐格式：

```text
公司整体：Watchlist / 待核验
- Thesis A：Excluded
- Thesis B：Watchlist — Early Optionality
- Thesis C：Shortlist
公司级风险覆盖：商誉 / 质押 / ST / 稀释 / 流动性
```

reconcile 规则：

1. **若所有 thesis 都 Excluded** → 公司级 Excluded；
2. **若至少一个 thesis Shortlist，但公司级财务/治理风险压倒** → 公司级 Watchlist 或 Excluded；
3. **若无 Shortlist，但存在 Early Optionality** → 公司级 Watchlist；
4. **若一个 thesis Excluded、一个 thesis Watchlist** → 公司级不能写 Shortlist；
5. **若公司级风险是退市/ST/重大财务造假/持续经营压力** → 覆盖所有 thesis。

公司级结论是风险汇总，不是 alpha 判断本体。

### 5. 已知会失真的情况

1. **thesis 切得太细**：每个概念都拆一条，会制造噪音。解决：必须满足“业务入口 + 客户/场景 + 时间窗口”才算 thesis。
2. **公司公告只否认一部分**：例如否认机器人，不等于否认液冷。解决：公告反证必须绑定具体 thesis。
3. **公司级财务风险覆盖所有 thesis**：即使某 thesis 成立，商誉、债务、ST、退市风险也可能压倒。解决：公司级风险单独覆盖。
4. **行业 thesis 被误当公司 thesis**：行业需求真实，不等于公司受益。解决：公司入口单独验证。
5. **旧 thesis 换壳复活**：被否认后换成新概念继续炒。解决：保留 thesis version history。

## 8.3 公告反证 6 级样本校准

### 1. 6 级反证判断标准

#### Level 1：完全否认

判断问题：

- 公司是否明确说“不涉及 / 不生产 / 无相关业务”？
- 是否否认核心产品、客户、订单或供应关系？
- 否认对象是否直接命中当前 thesis？

处理：

- 命中的 thesis → Excluded；
- 其他 thesis 不自动排除，但必须重新命名和验证。

#### Level 2：当前无规模化

判断问题：

- 公司是否说“尚未规模化”“未量产”“处于研发/试样/验证阶段”？
- 是否没有批量订单、稳定客户或持续收入？
- 市场 thesis 是否依赖“已经规模化兑现”？

处理：

- 当前兑现型 thesis → Excluded；
- 未来 optionality thesis → Watchlist — Early Optionality，必须写 checkpoint。

#### Level 3：占比低

判断问题：

- 公司是否明确说相关业务收入占比较低？
- 是否低于 materiality 门槛，且无合同金额+时间补足？
- 市场是否已经按主线业务在定价？

处理：

- 主线重估 thesis → Excluded；
- 早期观察 thesis → Watchlist，但不能进 Shortlist。

#### Level 4：存在不确定性

判断问题：

- 公司是否说业务推进、客户拓展、订单落地、量产时间存在不确定性？
- 不确定性是技术、市场、客户、监管、整合还是交付？
- 是否已有入口，但缺确认？

处理：

- Watchlist — Early Optionality；
- 必须绑定具体 fallback checkpoint。

#### Level 5：尚未产生收入

判断问题：

- 公司是否已有产品、项目、客户或合同，但尚未确认收入？
- 是否披露了收入确认时间窗口？
- 是否有订单/合同金额支持未来 materiality？

处理：

- Watchlist；
- 若有合同金额+时间，可接近 Shortlist，但收入未确认前仍需标注风险。

#### Level 6：业务正常 / 模板降温

判断问题：

- 公告是否只是“生产经营正常”“无应披露未披露事项”？
- 是否没有直接否认具体业务？
- 是否属于异动公告模板语言？

处理：

- 不构成 thesis 反证；
- 只加 R2 风险标签，提示市场热度升温。

### 2. 6 级之间最容易混的边界

#### Level 1 vs Level 6

“无应披露未披露事项”不是完全否认；“不生产 / 不涉及 / 无相关业务”才是完全否认。

#### Level 2 vs Level 5

“无规模化”比“尚未产生收入”更强。前者说明商业化程度不足，后者可能已有订单或项目但尚未确认收入。

#### Level 3 vs Level 4

“占比低”是 materiality 问题；“存在不确定性”是兑现路径问题。占比低更接近 Excluded，存在不确定性更接近 Watchlist。

#### Level 4 vs Level 5

“存在不确定性”可能连合同和客户都没闭合；“尚未产生收入”通常至少有更明确的业务入口。

### 3. 校准样本来源

优先级：

1. **巨潮资讯 / 上交所 / 深交所公告原文**  
   异动公告、澄清公告、风险提示、问询函回复、收购公告、财报。
2. **监管问询函与回复**  
   适合校准“占比低”“不确定性”“商誉/并表风险”。
3. **公司投资者关系记录 / 调研纪要**  
   可辅助判断业务入口，但权重低于公告。
4. **雪球 / 东方财富 / 同花顺公告摘要**  
   只作为发现入口，不能替代公告原文。
5. **媒体报道 / 券商研报**  
   可作为传播阶段证据，不作为公告反证本体。

### 4. 校准流程

建议每轮 R4 pressure test 后校准一次，不要等到 skill 成型后再补。

流程：

1. 收集 10-20 条 A 股异动公告/澄清公告样本；
2. 每条绑定一个具体 thesis，而不是绑定公司整体；
3. 标注 6 级反证等级；
4. 记录当时分桶决策；
5. 用后续公告、财报、订单或股价退潮验证是否误判；
6. 对误判样本更新边界规则。

verify 标准：

- 同一句公告语言，在相似 thesis 上应落到同一级；
- 不能因为后验股价上涨就改判；
- 只有后续订单、收入、合同、并表或公司再次澄清，才能修正规则。

### 5. 跟 8.1 的衔接：反证强度 × thesis-level 分桶

公告反证必须作用在 thesis，不默认作用在公司整体。

分桶矩阵：

- Level 1 完全否认 × 命中 thesis → Excluded；
- Level 2 当前无规模化 × 当前兑现型 thesis → Excluded；
- Level 2 当前无规模化 × 未来 optionality thesis → Watchlist — Early Optionality；
- Level 3 占比低 × 主线重估 thesis → Excluded；
- Level 3 占比低 × 早期观察 thesis → Watchlist；
- Level 4 存在不确定性 → Watchlist — Early Optionality；
- Level 5 尚未产生收入 → Watchlist；
- Level 6 业务正常 → 不改分桶，只加 R2 风险标签。

公司级 reconcile：

- 若公告只否认某一 thesis，只排除该 thesis；
- 若公告否认公司所有相关业务入口，公司级 Excluded；
- 若公告不否认但提示不确定性，公司级不进 Shortlist；
- 若公司级财务/治理风险压倒，覆盖所有 thesis。

### 6. 媒体订单不能作为 confirmation

媒体披露“订单正在交付”“产能扩张”“客户推进”等信息，只能作为 catalyst 或线索，不能作为 materiality proof。升级为 confirmation 至少需要合同金额+时间、客户订单、公告原文、财报 segment revenue，或多个独立来源的可核验交叉验证。若只有媒体口径，分桶最高为 Watchlist — Early Optionality，并必须写明缺失 checkpoint。

