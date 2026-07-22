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
3. **Scan the genre / shell landscape across 5-9 peer venues** — 写作前广扫同类型文章形态光谱，避免内核正确但形态无处可发
4. **Learn the target venue through 2-3 exemplars before drafting** — 写作前学 venue 的隐性规范
5. **Lock the master outline through reviewer rounds before drafting** — 写作前通过多轮 reviewer 反馈锁定题目 / 节结构 / 子节论点 / 图表配置
6. **Build a citation bank upstream of claim-evidence mapping** — 引用先入候选池（3× ratio + 80% recency + 每条 justification）
7. **Run a concept naming pass — every paper must produce one sticky concept** — 每篇 paper 必须产出一个可被引用的概念命名
8. **Map claim to evidence at three layers** — claim ↔ evidence 三层定位
9. **Per-unit writing rationale matrix** — 每一段都要解释为什么写、对齐什么 motivation
10. **Identify methodology spin-off candidates — don't bury the method in §3.2** — 识别可独立成方法论 paper 的组件
11. **Anonymize / data-governance review** as a gate — 脱敏与数据治理作为门槛
12. **AI research failure-mode checklist (7 modes)** — 失败模式清单（含引文幻觉 / 实现 bug / 结果幻觉等）
13. **Integrity gate (5 phases)** — 形式层验证 gate
14. **Persistent venue profiles + per-venue format gate** — 把每篇现学的 venue 知识沉淀为可复用的按刊档案，投稿前跑一道纯格式/体例核对（专治摘要标点、参考文献体例、双语缺失等低级退稿）
15. **Rebuttal workflow (4 phases)** — R&R 后的 concern 拆解 → 策略锁定 → 草稿 → safety check，防硬刚和盲从两种失败模式
16. **Reviewer-committee pre-screen** (optional) — 可选预审稿委员会：按刊校准严格度、独立多视角报告、major concern 须过 real/specific/addressable 对抗核验、输出 decision band + 1-3 个决定性问题（不输出假的录用概率）
17. **Journal match + resubmission ladder** — 选刊显式化：五信号画像 → 五维评分 → reach/match/safe 三档清单，投第一家之前就锁定退稿后的重投阶梯

## Repository structure

```
PaperForge/
├── README.md                # this file
├── SKILL.md                 # skill definition (for Claude / Codex / OpenAI agents)
├── QUICKSTART.md            # quickstart with 14-file workflow
├── docs/
│   └── roles.md             # agent role decomposition (writer / reviewer / verifier / style-polisher)
├── templates/               # 20 workflow templates (markdown + JSON)
│   ├── topic_selection_template.md
│   ├── scoping_review_template.md
│   ├── question_lock_template.md
│   ├── motivation_lock_template.md
│   ├── genre_landscape_scan_template.md
│   ├── exemplar_learning_dossier_template.md
│   ├── master_outline_lockin_template.md       # NEW (v0.6: multi-round outline lock-in)
│   ├── citation_bank_template.md
│   ├── source_inventory_template.md
│   ├── paper_protocol_template.md
│   ├── claim_evidence_matrix_template.md
│   ├── writing_rationale_matrix_template.md
│   ├── failure_mode_checklist_template.md
│   ├── integrity_gate_template.md
│   ├── revision_gate_template.md
│   ├── rebuttal_workflow_template.md          # NEW (v0.5: 4-phase R&R handling)
│   ├── venue_profile_template.md              # NEW (v0.7: persistent per-journal profile)
│   ├── venue_format_standards_template.md     # NEW (v0.7: pre-submission format gate)
│   ├── journal_match_template.md              # NEW (v0.8: reach/match/safe shortlist + resubmission ladder)
│   ├── human_style_policy_template.md
│   └── paper_state_template.json
├── venue_profiles/          # NEW (v0.7): reusable per-journal profiles (built once, reused per submission)
│   ├── INDEX.md                               # NEW (v0.8: research-profile-scoped ring index, 34 venues; full profiles built on shortlist only)
│   ├── 图书情报工作.md
│   ├── 现代情报.md
│   ├── 情报理论与实践.md
│   └── 研究生教育研究.md
├── LICENSE                  # MIT
└── CITATION.cff
```

## Version history

- **v0.8** (2026-07-15) · Venue-selection + committee-protocol upgrade, absorbed from `awesome-journal-skills` v1.0's new cross-journal capability layer (`shared-resources/`): (1) `journal_match_template.md` (Step 4.56 — five-signal paper profile → five-dimension scoring → reach/match/safe three-tier shortlist → pre-committed resubmission ladder; run when the target journal is undecided and re-run after any rejection; candidate venues must have a `venue_profiles/` entry before comparison). (2) Reviewer Committee protocol hardened (Step 6): venue-calibrated strictness, desk-screen-first ordering, independent distinct-lens reports, adversarial verification of every major concern (real + specific + addressable, else downgraded), decision-band output with 1-3 decisive issues mapped to owning workflow files, and a no-false-green rule (UNKNOWN ≠ PASS). Motivated by the post-reject re-targeting having been done entirely by hand. Plus `venue_profiles/INDEX.md`: a research-profile-scoped venue ring index (中文图情 / 教育与教育技术 / 科学学与科研管理 / English LIS & HE — 34 venues) adapting `awesome-journal-skills`' venue-index.tsv idea to a single-author workflow: index rows are cheap, full profiles are built only when a venue enters a shortlist; where the upstream repo has a matching pack (科学学 cluster, 电子政务), the index points to it as a verified-before-use drafting source.
- **v0.7** (2026-06-22) · Persistent venue-knowledge upgrade: `venue_profile_template.md` (Step 4.62 — sediment per-paper venue learning into reusable, cached per-journal profiles) + `venue_format_standards_template.md` (Step 7.6 — pure format/style gate keyed to the venue profile, separate from integrity_gate). Seed profiles built for 图书情报工作 / 现代情报 / 情报理论与实践 / 研究生教育研究. Absorbs the *persistent per-journal knowledge* architecture from Stanford REAP/CoPaper.AI `awesome-journal-skills` (builds only the venues PaperForge actually submits to, not the upstream English-journal content packs). Motivated by a real 《图书情报工作》 desk-reject faulted for abstract punctuation + format inconsistencies.
- **v0.6** (2026-05-27) · Outline-lock upgrade: `master_outline_lockin_template.md` (Step 4.65 — iteratively lock title, section structure, subsection arguments, and figure/table config through multiple reviewer rounds before drafting). Closes the gap between "why / what shell / what style" (upstream steps) and "what each section actually argues" (the drafting interface).
- **v0.5** (2026-05-25) · Form/shell + R&R upgrade: `genre_landscape_scan_template.md` (scans 5-9 peer venues for form/shell distribution before exemplar learning, prevents "right kernel but no venue accepts the form" failure) + `rebuttal_workflow_template.md` (4-phase R&R handling distilled from peer paper-skill work).
- **v0.4** (2026-05-24) · Series & branding upgrade: Step 4.8 Concept Naming Pass (every paper must produce one sticky concept) + Step 6.4 Methodology Spin-off Check (don't bury the method). Distilled from sustained study of high-output IS scholars.
- **v0.3** (2026-05-24) · PaperSpine-inspired upgrade: motivation_lock + exemplar_learning_dossier + citation_bank + writing_rationale_matrix. Forms a complete "writing preparation" layer.
- **v0.2** (2026-05-18) · ARS-inspired upgrade: failure_mode_checklist (7 modes) + integrity_gate (5 phases) + 3-layer citation locator in claim_evidence_matrix + Material Passport in paper_state.json. Forms a complete "back-end quality gate".
- **v0.1** (initial) · Topic funnel + question lock + claim-evidence matrix + revision gate + role split.

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
