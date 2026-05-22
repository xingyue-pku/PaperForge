# AI Research Failure Mode Checklist

> 实证根据：Lu et al. (2026) *Nature* 651(8107):914-919 — AI Scientist 全流程论文生成已通过 workshop 同评，作者本人提示该系统会 "tax overwhelmed review systems and add noise to scientific literature"。本清单把这些失败模式落实成可勾选的核查项，作为每一轮 revision gate 前的强制步骤。

## 使用规则

1. 每一个稿件版本在跨出 drafting 进入 review / submission 前必须填一次此表
2. 七模式中**任一项**进入 `SUSPECTED` 或 `CONFIRMED` 即触发 BLOCK：不允许进入下一阶段，直到降为 `CLEAR` 或被显式标记为 `ACCEPTED_RISK`（需写明承担理由与审稿应对）
3. 不允许"快速过表"，每条至少给出一个具体证据指针（文件、段落、表号、引用条目）

## 七模式核查表

### 模式 1 · Hallucinated Citations 引文幻觉

定义：引用的文献不存在 / 标题被改写 / 作者错位 / DOI 无效。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 每条 in-text 引用均能在参考列表定位 | CLEAR / SUSPECTED / CONFIRMED | |
| 每条参考列表项可在外部库（CrossRef / Semantic Scholar / Google Scholar）找到原始 metadata | | |
| AI 辅助生成的段落中所有引用均经独立核对 | | |
| 中文文献的题名、刊名、卷期、页码逐项校验 | | |

实证背书：Zhao et al. (2026) 在 4 平台 1.11 亿条引用中保守估算 2025 年单年新增 146,932 条幻觉引用，AI-writing 语言痕迹稿件密集分布。

### 模式 2 · Implementation Bugs 实现 bug

定义：代码、实验脚本、统计计算存在错误但被当作正确结果使用。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 所有实验脚本可复现（seed 固定 / 数据路径明确） | | |
| 关键统计量手算 / 第二脚本独立复核 | | |
| 单位 / 样本量 / 自由度等基本量已对账 | | |

### 模式 3 · Hallucinated Results 结果幻觉

定义：表格 / 数字 / 图表内容在原始数据中并不存在或不可追溯。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 每个文中数字可定位到 `data/` 或 `tables/` 中的源文件 | | |
| 每张图可从源数据脚本一键重生 | | |
| 引述他人结果时数字与原文一致（含小数位） | | |

### 模式 4 · Shortcut Reliance 捷径依赖

定义：模型 / 方法 / 论证靠未声明的捷径而非声明的机制达成结论。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 模型 / pipeline 没有依赖 ground truth 泄漏 | | |
| 评测集与训练集间无未声明的覆盖 | | |
| 主张的机制有 ablation / 消融可证伪 | | |

### 模式 5 · Methodology Fabrication 方法编造

定义：描述的方法步骤与实际执行不符；或方法步骤为事后修饰生成。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 方法节中每一步骤可在脚本 / 笔记中找到对应执行记录 | | |
| 数据预处理 / 排除标准与实际过滤日志一致 | | |
| 报告的超参数 / 阈值与最终实验设置一致 | | |

### 模式 6 · Frame-Lock 框架锁死

定义：分析框架已被先入观点锁定，反例 / 异常被悄悄丢弃或重新归类。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 反例 / 失败案例被显式记录而非剔除 | | |
| 主张存在反向证据时被显式讨论 | | |
| 编码 / 标注存在过渡分类时记录于审计日志 | | |

### 模式 7 · Bug-As-Insight 把 bug 当洞见

定义：因实现错误产生的"反直觉发现"被当作贡献，但实为 bug 副产物。

| 检查项 | 状态 | 证据指针 |
|---|---|---|
| 每个"反直觉发现"经过至少一次独立复算 | | |
| 异常值 / 极端结果有数据层面的源头解释 | | |
| 贡献声明不依赖任何尚未稳定复现的现象 | | |

## 结论行

- 是否所有 7 模式均为 CLEAR：是 / 否
- 若否：列出仍为 SUSPECTED / CONFIRMED 的模式及处置计划
- 是否有 ACCEPTED_RISK：列出哪几条，理由，对审稿的回应预案

## 引用

- Lu, C., Lange, R. T., Yamada, Y., Hu, S., Foerster, J., Ha, D., & Clune, J. (2026). Towards end-to-end automation of AI research. *Nature*, 651(8107), 914-919.
- Zhao, Z., Wang, Y., Stuart, T., De Vaan, M., Ginsparg, P., & Yin, Y. (2026). LLM hallucinations in the wild: Large-scale evidence from non-existent citations. *arXiv preprint* arXiv:2605.07723.
