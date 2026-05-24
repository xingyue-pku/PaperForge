# Writing Rationale Matrix

> 用途：每个论文 unit（章 / 节 / 子节 / 关键段落）都必须填一行 rationale，说明它为什么存在、怎么服务于 motivation、参照了什么 prior work / venue norm。
>
> 这是 PaperForge 最强的"deep revision only"防御机制：当 reviewer 让你大改时，你能直接对照本表判断哪些 unit 是结构性的、哪些是 cosmetic 的——避免把 deep revision 做成 shallow patch。
>
> 一句话总结：**没有 rationale 的 unit 不允许出现在最终稿中**。

## 实证背书

- PaperSpine 设计哲学：rationale matrix 是 audit 阶段的核心验证项
- 与 [[failure_mode_checklist_template]] 中 "frame-lock" 模式互补——本表防止 unit 因为惯性继续存在

## 控制框架行（第一行，必填）

整篇 paper 的 rationale 控制框架，必须先于任何 unit 行填写：

| 字段 | 内容 |
|---|---|
| **controlling_motivation** | 来自 motivation_lock 的一句话 motivation |
| **target_venue** | 目标期刊 / 会议 |
| **target_audience_primary** | 主读者群 |
| **paper_arc** | 整篇 paper 的故事弧（如：default → tension → action → twist → so what）|
| **min_evidence_set** | paper 存活所需的最低证据集合 |
| **out_of_scope** | 显式排除的论题（避免 unit 漂移）|

## Unit Rationale Rows

每个 unit 一行。Unit 粒度建议：章节 + 子节 + 关键论证段落。

| unit_id | unit_name | what_it_does | motivation_alignment | sota_pattern_or_anchor | target_venue_norm | user_evidence_source | planned_final_check |
|---|---|---|---|---|---|---|---|
| U01 | §1 Introduction | | | | | | |
| U02 | §1.1 Hook 段 | | | | | | |
| U03 | §1.2 张力段 | | | | | | |
| U04 | §1.3 Contribution 段 | | | | | | |
| U05 | §2 Related Work | | | | | | |
| U06 | §3 Method | | | | | | |
| ... | | | | | | | |

### 字段说明

- **unit_id**：稳定 ID（U01, U02...）。一旦分配，即使 unit 被删除，ID 不复用——以保留追溯历史
- **unit_name**：可读名称
- **what_it_does**：1-2 句话，**功能性**描述（如"建立 reviewer alignment 问题的研究张力"），不是"summarize results"
- **motivation_alignment**：明确说该 unit 推动 motivation 哪一环。如果填不出 → 该 unit 不应存在
- **sota_pattern_or_anchor**：参照了哪篇强论文的对应章节写法（如"Kuznetsov 2024 §1 风格"）
- **target_venue_norm**：目标期刊在该 unit 上的惯例（如"IPM intro 通常 1.5 页且含 explicit contribution sentence"）
- **user_evidence_source**：该 unit 引用的关键证据出处（数据表 / 文献 / 内部分析）
- **planned_final_check**：投稿前必须通过的具体 check（如"contribution sentence 必须 ≤ 50 词且不用'first'"）

## 维护规则

1. **任何新增 unit** 必须先填 rationale 行才能写正文
2. **任何删除 unit** 必须在本表对应行加 `DELETED YYYY-MM-DD + 原因`，不要直接删除（保留 audit trail）
3. **任何 unit 重写**（≥ 50% 内容变化）必须更新 what_it_does + planned_final_check
4. **integrity gate 前**必须对照本表 review 全部 unit
5. **revision gate 前**必须确认本表所有 planned_final_check 都已通过

## Audit 触发条件（自检）

提交前自问以下问题，若任一为 NO → 修复或删除：

| 自检项 | 含义 |
|---|---|
| 每个 unit 是否能从 motivation 推出？ | 否则 unit 在叙事中是孤儿 |
| 是否存在"为完整性而存在"的 unit？ | 例如"为了像综述所以加了 Bibliometric Analysis 节"——这类 unit 应删 |
| 是否每个 unit 都至少引用一个 prior anchor？ | 否则可能是"凭空创造"的论证 |
| 是否每个 unit 的 planned_final_check 都通过？ | 否则 unit 没准备好进入投稿 |
| 是否有 unit 跨越多个 motivation 维度？ | 跨越通常说明叙事不收敛，要么拆 unit 要么收 motivation |

## Deep Revision 防御使用方式

当审稿人提反馈时：

1. 把审稿意见 map 到具体 unit_id
2. 对照该 unit 的 rationale → 判断意见是 cosmetic 还是 structural
3. 如果 structural：rationale 必须更新 + 受影响的下游 unit 也要更新 rationale
4. 如果 cosmetic：只动 unit 正文，rationale 不变

**禁止**：因 reviewer 反馈直接动正文而不更新 rationale → 这会导致 paper 后续的逻辑漂移

## 引用

实证基础：PaperSpine SKILL.md (WUBING2023/PaperSpine)，方法论根基与 Alvesson & Sandberg (2020) problematizing review 的"deep engagement with literature"立场一致。

Linked: [[motivation_lock_template]], [[failure_mode_checklist_template]], [[revision_gate_template]]
