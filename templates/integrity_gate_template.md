# Integrity Gate

> 用途：在 revision gate 之前 / 投稿前，进行形式层的 5 阶段验证。
> 这一层只查"是否真"，不查"是否好"。
> 内容层（claim 是否站得住、贡献是否够、venue 是否合）由 revision_gate.md 负责。
> 任一阶段未通过则 BLOCK，不允许进入投稿或 reviewer committee 环节。

## Phase 1 · References Completeness & Formatting 引用完整与格式

| 检查项 | 状态 | 备注 |
|---|---|---|
| 所有 in-text 引用均出现在参考列表 | PASS / FAIL | |
| 所有参考列表条目均被 in-text 引用 | | |
| 引用格式与目标期刊一致（APA / GB/T / IEEE 等） | | |
| 中文 / 英文混合引用风格统一 | | |
| DOI / arXiv ID / URL 可访问 | | |

## Phase 2 · Citation Context Accuracy 引用上下文准确

| 检查项 | 状态 | 备注 |
|---|---|---|
| 每条引用在原文中**真的支持**所引的论点（非望文生义） | | |
| 引用页码 / 章节定位准确（直接引语必填） | | |
| 二次引用（A 引 B 中的 C）已显式标记 | | |
| 关键反对意见 / 边界条件未被截断 | | |

注：本阶段强烈建议结合 `claim_evidence_matrix.md` 的 3-layer citation locator 完成。

## Phase 3 · Statistical Data Validation 统计数据校验

| 检查项 | 状态 | 备注 |
|---|---|---|
| 表格 / 图中所有数字可追溯到 `data/` 或 `tables/` 源文件 | | |
| 报告的 N、df、效应量、p 值彼此一致 | | |
| 百分比与原始计数对账无误 | | |
| 图与表叙述与数字一致 | | |

## Phase 4 · Originality / Plagiarism Screening 原创性筛查

| 检查项 | 状态 | 备注 |
|---|---|---|
| 自引 / 系列工作衔接已声明 | | |
| 与已发表草稿 / 预印本的重复段落已重写或显式标注 | | |
| 直接引语 / 长句借用已 quote 并给出页码 | | |
| 不存在他人段落的隐式复制 | | |

## Phase 5 · Claim-to-Source Alignment 论点-证据对齐

| 检查项 | 状态 | 备注 |
|---|---|---|
| `claim_evidence_matrix.md` 中每条 main claim 状态为 `verified` | | |
| 抽样审计：随机抽 ≥ 20% 的关键引用做完整三层定位 | | |
| 讨论 / 结论的每一句结论性陈述均能在结果章找到出处 | | |
| 与主张矛盾的证据被显式讨论或写入 limitations | | |

## Stage Gate Decision

| Phase | Status | Blocker 数 |
|---|---|---|
| 1 References | | |
| 2 Citation Context | | |
| 3 Statistical Data | | |
| 4 Originality | | |
| 5 Claim-Source | | |

- 总判定：PASS / BLOCK
- 若 BLOCK：列出每一处具体待修

## 必备前置文件

- `claim_evidence_matrix.md`（3-layer locator 已填）
- `failure_mode_checklist.md`（7 模式均 CLEAR 或显式 ACCEPTED_RISK）

## 引用

实证背书同 `failure_mode_checklist_template.md`：Lu et al. (2026, Nature) + Zhao et al. (2026, arXiv 2605.07723)。
