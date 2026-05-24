# PaperForge

**A protocol-driven academic writing workflow for method, empirical, and data-analysis papers.**
**一个面向方法、实证、数据分析类论文的协议化学术写作工作流。**

---

## What is PaperForge

PaperForge is not a "write-the-paper-faster" tool. It is a **protocol pack** that turns scattered research material into a publishable draft through explicit checkpoints.

PaperForge 不是"让论文写得更快"的工具。它是一个**协议包**：把零散的研究材料，通过显式的检查点，转化为可投稿的论文初稿。

It sits between you and the temptation to start freeform drafting before:

- topic selection is locked
- the research question is anchored
- claims and evidence are aligned
- failure modes are identified
- integrity gates are passed

在以下几件事还没完成时，PaperForge 阻止你直接开写：

- 选题尚未收束
- 研究问题尚未锁定
- 论点与证据未对齐
- 失败模式未识别
- 完整性 gate 未通过

## Who is this for

- PhD students doing method, empirical, or data-analysis papers
- Researchers who keep getting trapped in "draft → rewrite → draft → rewrite" cycles
- Anyone using LLM agents (Claude, GPT, Codex) and worried about evidence-claim drift
- Teams that want a shared protocol for paper review before journal submission

- 写方法/实证/数据分析类论文的博士生
- 在"起草 → 重写 → 再起草 → 再重写"循环里反复挣扎的研究者
- 用 LLM 智能体（Claude / GPT / Codex 等）写论文、担心论点-证据漂移的人
- 想在投稿前先用协议化方式做预审的研究团队

## Core ideas

1. **Lock the topic before drafting** — 起草前先锁选题
2. **Lock the motivation before paper protocol** — 锁住"为什么读者要 care"才进入协议
3. **Learn the target venue through 2-3 exemplars before drafting** — 写作前学 venue 的隐性规范
4. **Build a citation bank upstream of claim-evidence mapping** — 引用先入候选池（3× ratio + 80% recency + 每条 justification）
5. **Map claim to evidence at three layers** — claim ↔ evidence 三层定位
6. **Per-unit writing rationale matrix** — 每一段都要解释为什么写、对齐什么 motivation
7. **Anonymize / data-governance review** as a gate — 脱敏与数据治理作为门槛
8. **AI research failure-mode checklist (7 modes)** — 失败模式清单（含引文幻觉 / 实现 bug / 结果幻觉等）
9. **Integrity gate (5 phases)** — 形式层验证 gate
10. **Reviewer-committee pre-screen** (optional) — 可选预审稿委员会

## Repository structure

```
PaperForge/
├── README.md                # this file
├── SKILL.md                 # skill definition (for Claude / Codex / OpenAI agents)
├── QUICKSTART.md            # quickstart with 14-file workflow
├── docs/
│   └── roles.md             # agent role decomposition (writer / reviewer / verifier / style-polisher)
├── templates/               # 15 workflow templates (markdown + JSON)
│   ├── topic_selection_template.md
│   ├── scoping_review_template.md
│   ├── question_lock_template.md
│   ├── motivation_lock_template.md            # NEW (v2: PaperSpine-inspired)
│   ├── exemplar_learning_dossier_template.md  # NEW (v2)
│   ├── citation_bank_template.md              # NEW (v2)
│   ├── source_inventory_template.md
│   ├── paper_protocol_template.md
│   ├── claim_evidence_matrix_template.md      # upgraded (v1: 3-layer locator)
│   ├── writing_rationale_matrix_template.md   # NEW (v2)
│   ├── failure_mode_checklist_template.md     # v1: 7-mode AI research failure modes
│   ├── integrity_gate_template.md             # v1: 5-phase formal-layer verification
│   ├── revision_gate_template.md
│   ├── human_style_policy_template.md
│   └── paper_state_template.json              # v2: includes motivation_lock / exemplar / citation_bank / rationale_matrix / integrity_gate / failure_mode_checklist / material_passport fields
├── LICENSE                  # MIT
└── CITATION.cff
```

## Version history

- **v2** (2026-05-24) · PaperSpine-inspired upgrade: motivation_lock + exemplar_learning_dossier + citation_bank + writing_rationale_matrix. Forms a complete "writing preparation" layer.
- **v1** (2026-05-18) · ARS-inspired upgrade: failure_mode_checklist (7 modes) + integrity_gate (5 phases) + 3-layer citation locator in claim_evidence_matrix + Material Passport in paper_state.json. Forms a complete "back-end quality gate".
- **v0** (initial) · Topic funnel + question lock + claim-evidence matrix + revision gate + role split.

## How to use

### Option A — As a Claude / Codex skill

Copy `SKILL.md` and `templates/` to your `.codex/skills/paperforge/` or `.claude/skills/paperforge/` directory. The agent will load it automatically when you invoke paper-writing tasks.

把 `SKILL.md` 和 `templates/` 复制到 `.codex/skills/paperforge/` 或 `.claude/skills/paperforge/` 目录，agent 会在你开启论文写作任务时自动加载。

### Option B — As a manual workflow

Open `QUICKSTART.md` and run through the 5-step process yourself, filling in templates as you go.

打开 `QUICKSTART.md`，按 5 步流程手动跑一遍，逐项填模板。

## License

MIT — see [LICENSE](./LICENSE)

## Citation

If you use PaperForge in your work, please cite it. See [CITATION.cff](./CITATION.cff).

## Author

**Yue Xing (邢玥)** · PhD candidate at Peking University, Department of Information Management
[github.com/xingyue-pku](https://github.com/xingyue-pku)
