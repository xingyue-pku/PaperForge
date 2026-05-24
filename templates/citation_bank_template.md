# Citation Bank

> 用途：在 `claim_evidence_matrix.md` 之前的一道**候选池建设**，确保 paper 的引用集合**不只是没有错（claim_evidence_matrix 任务），还要不漏不偏**。
>
> 与 claim_evidence_matrix 的分工：
> - **citation_bank**：候选池——是否有该引的没引、是否引偏方向、是否引用质量足够
> - **claim_evidence_matrix**：实际使用——每条已引用的引用是否真正支持其对应论点
>
> 二者必须配套使用。

## 实证背书

- PaperSpine 设计：default 60-paper candidate pool + 3× target ratio + 80% recency 规则
- Zhao et al. (2026, arXiv 2605.07723)：146,932 条幻觉引用证明无候选池治理的引用极易出错

## 建池规则

### 规则 1 · 3× target ratio

| 文章类型 | 目标引用数 | 候选池目标 |
|---|---|---|
| 短论文 / 通讯 | 15-20 | 45-60 |
| 中文 LIS 期刊综述 | 30-50 | 90-150 |
| 英文 IPM / JASIST | 40-70 | 120-210 |
| 博士论文章节 | 60-100 | 180-300 |

**为什么 3×**：实际引用率约 30-40%，候选池小于 3× 会让选择偏窄。

### 规则 2 · 80% recency

候选池中 80% 必须来自近 5 年（含目标投稿当年）。剩余 20% 用于：
- 奠基性老论文（如 Cohen 1960 的 Kappa）
- 制度文献（同评准则、政策文件）
- 必须性回应的对照锚（如 Kuznetsov 2024 这种 anchor 综述）

如果实际比例 < 80% recent → paper 容易被视为"对当前文献掌握不足"。

### 规则 3 · 每条候选必须带 justification sentence

不允许只写文献条目。每条候选必须有以下 4 字段：

| 字段 | 内容 |
|---|---|
| **citation** | 标准引用格式 |
| **target_use_section** | 拟用于哪个 unit（如 "§2.1 inter-rater reliability 综述"）|
| **why_in_pool** | 一句话说明为什么这篇值得候选 |
| **strength** | A / B / C 三档：A=必引，B=应引，C=候选 |

## 候选池主表

按主题分组，每组内按时间倒序。

### 组 1 · {主题 1，如 "Inter-rater reliability 方法学"}

| # | citation | target_use_section | why_in_pool | strength |
|---|---|---|---|---|
| 1 | Shrout & Fleiss (1979). Intraclass correlations: Uses in assessing rater reliability. *Psychological Bulletin*, 86(2), 420-428. | §3.2 ICC 模型选择 | ICC 经典方法论根基，必须引 | A |
| 2 | Krippendorff (2018). *Content Analysis*. 4th ed. | §3.2 α 计算依据 | Krippendorff α 唯一权威著作 | A |
| 3 | (...) | | | |

### 组 2 · {主题 2，如 "同行评议中的 reviewer 一致性"}

| # | citation | target_use_section | why_in_pool | strength |
|---|---|---|---|---|
| 1 | Cortes & Lawrence (2021). Inconsistency in conference peer review. *NeurIPS Experiment Report*. | §1 motivation + §2 related work | NeurIPS 复制实验的最强对照锚 | A |
| 2 | Stelmakh et al. (2023). A large scale randomized controlled trial on herding in peer-review discussions. | §2 / §5 discussion | 同评 herding 实证基础 | A |
| 3 | (...) | | | |

### 组 3 · {主题 3，如 "AI / LLM 辅助评议"}

| # | citation | target_use_section | why_in_pool | strength |
|---|---|---|---|---|
| 1 | Kuznetsov et al. (2024). What Can Natural Language Processing Do for Peer Review? | §2 + §5 future work | 当前最重要的英文对照综述 | A |
| 2 | Zhao et al. (2026, arXiv 2605.07723). LLM hallucinations in the wild. | §5 discussion (LLM 评议可信度) | 146,932 条幻觉引用的硬数字 | A |
| 3 | Lu et al. (2026, Nature). Towards end-to-end automation of AI research. | §1 motivation + §5 discussion | "AI Scientist 通过 workshop 同评"作为 anchor 反面案例 | A |
| 4 | (...) | | | |

### 组 N · {继续添加主题组}

## 池统计自检

填完候选池后，必须填以下统计：

| 自检项 | 当前值 | 目标 | 状态 |
|---|---|---|---|
| 候选总数 | | ≥ 3 × target_citation_count | |
| 近 5 年比例 | | ≥ 80% | |
| 中文文献比例（若投中文期刊）| | 至少 25-30% | |
| A 档（必引）数量 | | ≈ target_citation_count | |
| 每个 target_use_section 至少 3 候选 | | | |
| 不同主题组间无重大重叠 | | | |

任一项不达标 → 不允许进入 claim_evidence_matrix 阶段。

## 与 claim_evidence_matrix 的对接

claim_evidence_matrix.md 中每条 main claim 的 Layer 3 (Source Evidence) 字段，**只能从本 citation bank 的 A / B 档中选取**。

如果某 claim 需要引用的文献不在 bank 中 → 先把它加入 bank（带 justification）→ 再加入 matrix。这保证引用决策有 audit trail。

## 不允许出现的引用类型

- 来自候选池外的"临时引用"（写到一半为了凑数引的）
- 没有 justification sentence 的引用
- AI 生成时未经独立核对的引用（特别警惕引文幻觉）
- 自引但与本文论点无实质衔接的（影响新颖性论证）

## 状态变更日志

- YYYY-MM-DD · 初次建池，target = X 条，pool = Y 条
- YYYY-MM-DD · 新增组 Z（{原因}）

## 引用

实证基础：PaperSpine citation 设计 + Zhao et al. (2026) 引文幻觉实证数据。

Linked: [[claim_evidence_matrix_template]], [[failure_mode_checklist_template]], [[paper-zhao-2026-hallucinated-citations]]
