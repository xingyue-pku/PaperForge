---
name: paperforge
description: "Use when you need a protocol-driven academic writing workflow for a paper: topic selection, scoping review, research-question lock, claim-evidence alignment, revision gates, anonymization/data-governance checks, and turning scattered experiments into a publishable draft."
---

# PaperForge

Use this skill when the task is not just “write the paper”, but “set up a rigorous paper workflow” with explicit topic scoping, literature positioning, protocol, evidence mapping, and revision gates.

This skill is designed for method, empirical, and data-analysis papers that need:

1. topic selection and question lock before drafting
2. preliminary literature scouting and source organization
3. problem framing before drafting
4. claim-to-evidence control
5. anonymization and data-governance review
6. separation of methods, results, interpretation, style, and adversarial review
7. iterative drafting without losing logic
8. optional reviewer-committee pre-screen before integration (`PaperForge Reviewer Committee`)

## What This Skill Produces

For a new paper workspace, create these files first:

- `workflow/topic_selection.md`
- `workflow/scoping_review.md`
- `workflow/question_lock.md`
- `workflow/motivation_lock.md` (locks central argument before drafting)
- `workflow/exemplar_learning_dossier.md` (learns target venue's strong examples; produces target_scene_norms + style_profile)
- `workflow/citation_bank.md` (3× target ratio candidate pool, 80% recency, justification per entry)
- `notes/source_inventory.md`
- `workflow/paper_protocol.md`
- `workflow/claim_evidence_matrix.md` (with 3-layer citation locator; draws from citation_bank)
- `workflow/writing_rationale_matrix.md` (per-unit rationale; deep-revision-only defense)
- `workflow/failure_mode_checklist.md` (7-mode AI research failure modes)
- `workflow/integrity_gate.md` (5-phase formal-layer verification)
- `workflow/revision_gate.md`
- `notes/paper_state.json` (includes Material Passport fields for multi-session resume)
- `workflow/human_style_policy.md` (optional but recommended before final style polishing)
- `notes/methodology_spinoff_candidates.md` (created if Step 6.4 identifies spin-off candidates)

Then generate or revise:

- framing memos
- topic funnel and kill-list memos
- literature positioning memos
- data-governance memos
- methods/results/discussion drafts
- reviewer risk memos

## Core Rule

Do not start with freeform drafting.

If the topic is still fluid, do not even start the paper protocol.

Start with topic selection, scoping review, and question lock.
Only then move to protocol, evidence map, revision gate, and role-based drafting.

## Recommended Workflow

### Step 0. Run Discovery Before Protocol

Create a per-paper structure:

```text
your_paper/
  discovery/
  workflow/
  notes/
  drafts/
  data/
  tables/
```

Use the templates in `templates/`:

- `topic_selection_template.md`
- `scoping_review_template.md`
- `question_lock_template.md`
- `source_inventory_template.md`
- `paper_protocol_template.md`
- `claim_evidence_matrix_template.md`
- `revision_gate_template.md`
- `paper_state_template.json`
- `human_style_policy_template.md`

Create these discovery files first:

- `workflow/topic_selection.md`
- `workflow/scoping_review.md`
- `workflow/question_lock.md`
- `notes/source_inventory.md`

Use them to force an explicit funnel:

1. generate 3-5 candidate topics
2. score them on problem importance, evidence access, method tractability, venue fit, and likely contribution
3. kill weak or tool-led topics early
4. build a scoping corpus before claiming a gap
5. lock one question before protocol drafting

### Step 1. Fill the State First

Before drafting, fill `notes/paper_state.json` with:

- current phase
- candidate topics
- locked topic
- core research object
- preliminary search status
- working title
- target journal
- paper positioning
- main claim
- sub-claims
- scope and generalization boundary
- benchmark and method boundary
- red lines

### Step 2. Build the Topic Funnel

In `workflow/topic_selection.md`, force each candidate to answer:

1. what is the research object
2. what exact problem is unsolved
3. why now
4. what data or evidence is already accessible
5. what method path is realistic within the deadline
6. what venue or paper type naturally fits
7. what is the likely reviewer attack

Do not carry more than 2 live candidates after this step.

### Step 3. Build a Scoping Review, Not Just a Loose Reading List

In `workflow/scoping_review.md`, create:

1. search questions
2. seed papers
3. search strings and source list
4. inclusion and exclusion rules for the scoping pass
5. theme clusters
6. gap candidates
7. a short “what this paper is not” section

The goal is not a publishable review at this stage.
The goal is to verify that the paper can claim a real gap and stand on an organized source base.

### Step 4. Lock the Question Before Protocol

Use `workflow/question_lock.md` to freeze:

1. working title
2. one-sentence paper claim
3. primary research question
4. 2-4 sub-questions or hypotheses
5. data and method boundary
6. out-of-scope interpretations
7. minimum evidence needed for the paper to remain alive

If you cannot fill this file cleanly, the topic is not ready for drafting.

### Step 4.5. Lock the Motivation Before Protocol

`question_lock` locks the **scientific question**. `motivation_lock` locks **why the reader must care**. These are different layers — motivation cannot be derived from question alone.

Use `workflow/motivation_lock.md` to freeze:

1. one-sentence motivation: `{reader type} + {current default belief / gap} + {what this paper makes them reconsider}`
2. target audience (≤ 3 groups), with explicit exclusion of who this is NOT for
3. one-sentence "what the reader can do after reading"
4. mapping from `main_claim` (question_lock) to motivation (the "so what" jump)
5. three ranked contribution claims
6. why-now timing rationale
7. why-you rationale (private, not in paper)
8. why-not-others rationale (private)

This file forbids fillers like "本文意义在于…" / "首次研究…" / "希望对…有所启发". If motivation cannot be locked cleanly, do NOT proceed to drafting — return to scoping or question lock.

### Step 4.6. Learn the Target Venue Through Exemplars

Use `workflow/exemplar_learning_dossier.md` to **structurally study** 2-3 strong recent papers from the target venue, before drafting any substantive section.

Each exemplar must come from one of three categories:

1. same topic neighbor (closest research question)
2. same method neighbor (closest method, different topic)
3. same column top-tier (award / highly-cited from same section)

Each exemplar produces:

- per-section analysis (what they did / what to borrow / what to avoid duplicating)
- key sentence patterns (3-5 quotes per exemplar)

The dossier consolidates into two operable outputs:

- `target_scene_norms.md` — venue's implicit norms (intro length, contribution sentence form, related-work placement, etc.)
- `style_profile.md` — sentence length, paragraph density, term density, voice, tense, naming style

After drafting any major section, run a reverse audit against these two outputs. Explicitly decide for any deviation whether to align or deliberately diverge (with stated reason).

### Step 4.7. Build the Citation Bank

Use `workflow/citation_bank.md` to construct the upstream candidate pool that feeds Step 5's claim-evidence matrix.

Rules:

1. **3× target ratio** — candidate pool ≥ 3 × intended final citation count
2. **80% recency** — at least 80% of candidates from past 5 years
3. **per-entry justification sentence** required: `citation` + `target_use_section` + `why_in_pool` + `strength` (A=must, B=should, C=candidate)
4. organize candidates by topic group, ordered reverse-chronologically within group

Empirical basis for this discipline: Zhao et al. (2026, arXiv:2605.07723) audited 111M references across 4 platforms and conservatively estimated 146,932 hallucinated citations in 2025 alone — without a curated candidate pool, AI-assisted writing tends to fabricate or misattribute citations.

The claim-evidence matrix in Step 5 may only draw Layer 3 evidence from the A/B-tier entries in this bank. Any citation that bypasses the bank is forbidden in the final draft.

### Step 4.8. Run the Concept Naming Pass

Every PaperForge paper must produce **at least one sticky concept** — a noun phrase or acronym that future papers can cite and extend. Without one, the paper risks being remembered only as "that paper that found X" with no lasting citation handle.

Use a Concept Naming Pass to generate and lock the paper's sticky concept before drafting begins.

Naming constraints (all must hold):

1. **Noun phrase or acronym** — not a verb phrase, not a sentence
2. **Acronym-friendly (3-6 letters preferred)** OR **short phrase reusable in other papers** (e.g., "topic diversity", "attention inequality", "core-periphery structure")
3. **Differentiating** — search the literature; if the name or close variant already exists with a different meaning, reject or modify
4. **Computable / measurable** — future papers must be able to cite the name AND extend the measurement to new data (e.g., "CDAG of NeurIPS 2024 reviewers" should be a meaningful phrase)
5. **Motivation-aligned** — must directly express the locked motivation from Step 4.5

Procedure:

1. Generate 3 candidate names, ranked by strength
2. For each candidate, write a one-sentence differentiation check and a one-sentence measurability check
3. Pick one final name; record in `motivation_lock.md` under a new field `sticky_concept`
4. From this point on, the sticky concept must appear in: paper title (if possible), abstract first or last sentence, introduction's contribution sentence, and at least 5 times in the body

Empirical basis: Observation of citation patterns in information science suggests that successful paper lines are typically anchored by an early-paper-introduced sticky concept (a short noun phrase or acronym that later papers can both cite and extend). Papers without such anchors tend to be cited as "see also" but rarely as "we extend X's framework of Y".

### Step 5. Build the Claim-Evidence Matrix

Every major claim must have:

1. Layer 1 · claim statement
2. Layer 2 · in-draft position (file / section / paragraph)
3. Layer 3 · source evidence (data files & tables, or author + year + page + direct quote for external citations)
4. verification status (pending / sampled / verified / disputed)

If a claim cannot be mapped through all three layers, it cannot become a headline contribution.

### Step 6. Split Roles

Use separate roles for:

1. Topic Scoping
2. Literature Positioning
3. Problem Framing
4. Data Governance
5. Methods and Statistics
6. Results
7. Interpretation
8. Venue Style Editing
9. Adversarial Review

Optionally add a reviewer committee layer before integration, referred to as:

**PaperForge Reviewer Committee**

It includes:

1. Research Question & Contribution Reviewer
2. Data Governance & Method Transparency Reviewer
3. Literature Gap & Venue Fit Reviewer
4. Logic Chain & Evidence Mapping Reviewer
5. Desk Reject Editor Simulator

Never let one role write, interpret, and approve itself.

### Step 6.3. Build the Writing Rationale Matrix Before Drafting Each Unit

Use `workflow/writing_rationale_matrix.md` to record, for each manuscript unit (chapter / section / sub-section / key argumentative paragraph), the rationale of its existence.

The first row of the matrix is the **controlling framework** — the paper-level rationale (controlling motivation, target venue, paper arc, minimum evidence set, out-of-scope). Every subsequent row covers one unit with these fields:

- `unit_id` (stable; never recycled even after deletion)
- `what_it_does` (functional description, not result summary)
- `motivation_alignment` (which strand of motivation it advances)
- `sota_pattern_or_anchor` (which strong paper's corresponding section was referenced)
- `target_venue_norm` (venue convention for this unit type)
- `user_evidence_source` (data table or literature anchor)
- `planned_final_check` (specific check that must pass before submission)

Maintenance rules:

1. Any new unit requires a rationale row before any prose is written into it
2. Any deleted unit must be marked `DELETED YYYY-MM-DD + reason` in the row (do not remove rows, preserve audit trail)
3. Any unit with ≥ 50% content change requires updated `what_it_does` and `planned_final_check`
4. Before integrity gate, every unit's `planned_final_check` must pass
5. When reviewer feedback arrives, map each comment to specific unit_id and judge whether the comment is cosmetic or structural before acting

This matrix is the strongest defense against the "deep revision becomes shallow patch" failure mode and against unit-by-unit drift across revision rounds.

### Step 6.4. Identify Methodology Spin-off Candidates

Once the writing_rationale_matrix controlling framework is filled, evaluate whether the paper's method itself deserves a separate methods paper.

A spin-off is warranted when **all three** hold:

1. The paper's method contains **≥ 2 novel methodological components** that could each support a separate methods paper
2. The application domain in this paper is narrow enough that the method has cross-domain value not exhausted by this submission
3. There exists a distinct, fit venue for the method paper (e.g., main paper → IPM application; method paper → Journal of Informetrics methodology)

If yes to all three, record in `notes/methodology_spinoff_candidates.md`:

- candidate spin-off title
- which method components from main paper feed it
- target venue (must differ from main paper's venue)
- estimated 2-3 month writing gap after main paper submission
- decision date (when to commit or drop)

This step prevents the most common failure mode for method-heavy applied papers: the method is buried in §3.2 of an application paper, future papers cite the application but never the method. Spinning the method out gives it its own citation handle.

Empirical basis: Mature applied-research lines in information science routinely spin off methodology contributions into separate venues alongside application papers. The spin-off requires conscious early identification — burying the method first then trying to extract it later usually fails because the method becomes intertwined with application-specific decisions by the time anyone tries to lift it out.

### Step 6.5. Run the Integrity Gate Before Revision Gate

Before any revision-gate sign-off or submission round, run two formal-layer checks:

1. `failure_mode_checklist.md` — 7 modes from the AI research failure literature: hallucinated citations, implementation bugs, hallucinated results, shortcut reliance, methodology fabrication, frame-lock, bug-as-insight. Any mode in `SUSPECTED` or `CONFIRMED` blocks the gate.
2. `integrity_gate.md` — 5 phases: references completeness & formatting, citation context accuracy, statistical data validation, originality / plagiarism screening, claim-to-source alignment.

This step exists because:

- Lu et al. (2026, *Nature*) shows fully automated AI Scientist pipelines can already pass workshop-level peer review, surfacing the same failure modes at scale.
- Zhao et al. (2026, arXiv:2605.07723) audits 111M references across 4 platforms and conservatively estimates 146,932 hallucinated citations in 2025 alone, with disproportionate concentration in AI-uptake fields and AI-writing-style manuscripts.

These references are not optional folklore — they justify the existence of the integrity gate. Cite them in the methods section if the paper uses LLM assistance.

If integrity gate fails, do not proceed to revision gate.

### Step 7. Run the Revision Gate

Before each integration round, check:

0. `integrity_gate.md` and `failure_mode_checklist.md` have both signed off (Step 6.5)
1. the topic is locked and the question has not drifted
2. motivation lock (Step 4.5) is unchanged; if it has shifted, all downstream artifacts must be re-derived
3. literature positioning still matches the actual draft AND the citation_bank still covers all used citations
4. title, abstract, research questions, and contribution claims are aligned
5. all claims have evidence via 3-layer locator (and all evidence comes from citation_bank A/B tier)
6. anonymization is clean
7. supplementary validation is not overstated
8. discussion sentences can trace back to results
9. all writing_rationale_matrix `planned_final_check` items pass
10. drafted sections audit cleanly against `target_scene_norms.md` and `style_profile.md`
11. reviewer committee outputs do not contain unresolved desk-reject blockers
12. if a prose-risk pass is used, it follows `human_style_policy.md` and does not alter claims, citations, numeric meaning, or generalization boundary

If a blocker remains, do not proceed to the next integration round.

### Step 8. Optional Prose-Risk Pass

This pass is for final-round quality control, not detector evasion.

Use it only after:

1. claims are settled
2. evidence wording is settled
3. the revision gate has passed for substance

Allow it to do only four things:

1. remove generic stock phrases and assistant-like wording
2. reduce repetitive mechanical transitions and repeated sentence openings
3. calibrate overstrong certainty into defensible academic language
4. smooth mechanically uniform sentence rhythm when readability benefits

Do not use it to:

1. optimize for AI-detector scores or perplexity
2. introduce rare wording just to look less predictable
3. weaken technical precision or venue fit
4. change claims, citations, tables, numbers, or scope

## Discovery Standards

Use these standards during topic selection and early research:

1. prefer question-led topics over tool-led topics
2. do not claim a gap after reading only one line of work
3. keep a source inventory with why each source matters
4. separate “interesting idea” from “paperable question”
5. kill topics that require unavailable data, unavailable validation, or unstable novelty claims

## When To Use PaperForge vs. Other Research Skills

Use `PaperForge` when the goal is to turn a topic into a submission-ready paper workflow.

That includes:

1. topic funnel and question lock
2. scoping review and source organization
3. paper protocol and claim/evidence control
4. venue-fit drafting and pre-review gates

If the user only wants broad ideation or open-ended brainstorming, a lighter research skill may be enough.
If the user already has a locked question and draft assets, skip straight to protocol and revision control.

## Standard Calling Name

Within projects, you can refer to this pre-screen layer simply as:

- `PaperForge Reviewer Committee`

Example usage:

- “Use PaperForge Reviewer Committee to pre-screen the current manuscript before integration.”
- “Run a PaperForge Reviewer Committee round, then update the revision gate.”

## Anonymization and Governance

If the paper involves sensitive institutional or person-level data:

1. remove school names, person names, IDs, thesis titles, and raw traceable text
2. publish only anonymized, recoded, or aggregated variables
3. treat web pages, tables, appendices, examples, and quoted text under the same rule

If needed, create:

- `data_governance_protocol.md`
- `publishable_variable_set.md`
- `restricted_fields_blacklist.md`

## Journal Fit

When targeting a journal, do not only tune the language.

Also tune:

1. what counts as contribution
2. how methods are foregrounded
3. how aggressively results are interpreted
4. how much theory vs. application vs. benchmark design to show

## When To Read Extra Files

Read from `docs/` when you need:

- role definitions
- quickstart steps
- reusable protocol guidance

Use `templates/` when creating a new paper workflow.
