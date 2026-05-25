# Rebuttal Workflow

> 用途：在收到审稿意见后，按"concern 拆解 → 策略锁定 → 草稿 → safety check"四步处理，避免凭情绪硬刚或不假思索 yes-to-all。
>
> 触发：任何 paper 进入 R&R（Revise & Resubmit）状态后。如果 paper 在 acceptance / rejection 两端，本流程不适用。

## 实证背书

学术 rebuttal 失败的两种最常见模式：

1. **情绪驱动反驳**——把 reviewer 当对手而非读者，逐条针锋相对，最终编辑判 reviewer 一方
2. **无差别 yes-to-all**——所有意见都答"Done"，结果论文核心论点被悄悄改弱

本流程通过强制 4 步分隔（拆解 / 策略 / 草稿 / 检查），避免这两种模式。

## Step 1 · Concern Decomposition（拆解 reviewer 意见）

把每条 reviewer 意见拆成结构化条目：

| 字段 | 内容 |
|---|---|
| `concern_id` | 唯一 ID（R1-C1, R1-C2, R2-C1...）|
| `reviewer` | 哪位 reviewer（R1/R2/R3/AC）|
| `concern_type` | major / minor / clarification / writing / methodology / scope / claim_strength |
| `target_paper_unit` | 这条意见 map 到论文哪个 unit（用 writing_rationale_matrix 的 unit_id）|
| `verbatim_quote` | reviewer 原话（不复述）|
| `paraphrase` | 我对这条意见的理解 |
| `verifiable` | reviewer 是基于事实 / 还是基于偏好（factual / preferential / misread）|

**强制规则**：
- 每条意见拆完才能进下一步。**不允许"reviewer 都是错的"心理过滤**
- 不允许把"clarification 类"意见标为"major"（除非真的是核心争议）
- 若 reviewer 误读了你写的内容（misread），先反思：是 reviewer 真错，还是文字让人误读？

## Step 2 · Strategy Lock（策略锁定）

对每条 concern，选定一种处置策略：

| 策略 | 含义 | 适用 |
|---|---|---|
| **accept_fully** | 完全采纳意见，做对应修改 | 意见正确且修改不损害核心论点 |
| **accept_partial** | 采纳部分，保留部分立场 | 意见有理但全盘采纳会削弱论点；做局部修订 + 解释余下 |
| **clarify** | 论文未修改，但补充澄清 reviewer 误读处 | reviewer misread，修订文字让读者不再误读 |
| **respectful_disagree** | 不修改，理由充分论证 | 意见基于偏好或理解偏差；必须给出引用 / 数据级别的论证 |
| **defer** | 承认意见但留为 future work | 修改超出本稿 scope；要明说"out of scope for this submission" |

**强制规则**：
- `respectful_disagree` 比例不能超 25%（更高比例 = 编辑感觉你在硬刚）
- 任何修改主张强度（claim_strength 调整）的地方必须经 motivation_lock 核对——**不能因 reviewer 一句话削弱主 claim**
- 任何 `accept_fully` 涉及 ≥ 2 个 unit 的修改必须先更新 writing_rationale_matrix 对应行
- 跨多 reviewer 矛盾的意见（R1 说 X，R2 说 ¬X）必须单独标记，给出综合判断

## Step 3 · Response Draft（rebuttal 文字）

每条 concern 一段回复，模板：

```
**R{i}-C{j}** "{verbatim_quote 简短引用}"

We thank Reviewer {i} for this comment.

[Strategy 对应表述]
- accept_fully: "We have revised X to address this. See revised §{unit_id}, p.{n}."
- accept_partial: "We agree partially. We have revised {部分}. We respectfully retain {部分} because {理由 + 引用}."
- clarify: "This comment helped us identify that our original wording could be misread. We have revised §{unit_id} to make explicit that {澄清}."
- respectful_disagree: "We respectfully disagree. The original {claim} is supported by {evidence/citation}. We have added {additional context} to §{unit_id} to make this clearer."
- defer: "We agree this is an important direction. We have added it to Future Work (§N) but believe it is out of scope for the current submission because {理由}."

[Page / section reference where change is made]
```

**强制规则**：
- 每段回复 ≤ 6 句
- 必须含 page / section 引用（让 reviewer 能快速验证修订）
- 禁用："Thank you for the helpful comment" 类填充句（reviewer 知道你在客套）
- 禁用："We have improved..." 这种泛泛之词，必须具体说改了什么
- 禁用情绪化或防御性词："unfortunately", "obviously", "clearly the reviewer..."

## Step 4 · Safety Check（投出前自检）

提交前自查（强制全过）：

| 检查项 | 通过条件 |
|---|---|
| 主 claim 未被悄悄削弱 | motivation_lock 的 main_claim 在修订稿中仍然成立 |
| writing_rationale_matrix 同步更新 | 所有 `accept_fully` / `accept_partial` 涉及的 unit 行已更新 |
| 数字 / 引用一致性 | integrity_gate Phase 2 + Phase 3 复跑 |
| reviewer 之间矛盾意见有显式处理 | 不允许两边都答 yes |
| `respectful_disagree` 比例 ≤ 25% | 否则 review 策略偏硬，需要重审 |
| 修订摘要（cover letter to editor）有总结性表述 | 至少含：N 处采纳 / M 处部分采纳 / K 处澄清 / L 处保留立场（含理由）|
| 任何对 figure / table 的修改有 corresponding 文字更新 | 跨模态一致 |
| 修订追踪文件（marked-up version）跟 rebuttal letter 1:1 对应 | 编辑能逐条核对 |

任一项不通过 → 不允许提交。

## 强约束（red lines）

- **不允许"假装同意"**：accept_fully 必须真的修改，不能只在 rebuttal 写"已修改"实际未动
- **不允许"对人不对论"**：所有回复必须针对意见的内容，不评论 reviewer 的专业性 / 偏好 / 立场
- **不允许偷换概念**：reviewer 问 A，你回 B 并假装回答了 A
- **不允许过度自我表扬**：rebuttal 不是 sales pitch，是工程响应

## 文件产出

| 文件 | 内容 |
|---|---|
| `rebuttal/concerns_decomposed.md` | Step 1 拆解表 |
| `rebuttal/strategy_lock.md` | Step 2 策略表 |
| `rebuttal/rebuttal_letter_v{n}.md` | Step 3 草稿 |
| `rebuttal/safety_check_log.md` | Step 4 自检 |
| `rebuttal/cover_letter_to_editor.md` | 编辑可读的修订摘要（总数 + 大头 changes）|
| 跟稿件同步更新 | `writing_rationale_matrix.md` 各受影响 unit 行 |

## 与其他模板的关系

- 依赖 `motivation_lock.md`（不允许 rebuttal 中削弱 main_claim）
- 依赖 `writing_rationale_matrix.md`（受影响 unit 必须同步更新）
- 依赖 `integrity_gate.md`（Step 4 复跑 Phase 2/3）
- 依赖 `failure_mode_checklist.md`（如 reviewer 指出引文 / 结果 / 方法问题，重跑对应模式）
