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
- `notes/source_inventory.md`
- `workflow/paper_protocol.md`
- `workflow/claim_evidence_matrix.md` (with 3-layer citation locator)
- `workflow/failure_mode_checklist.md` (7-mode AI research failure modes)
- `workflow/integrity_gate.md` (5-phase formal-layer verification)
- `workflow/revision_gate.md`
- `notes/paper_state.json` (includes Material Passport fields for multi-session resume)
- `workflow/human_style_policy.md` (optional but recommended before final style polishing)

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

Use the templates in `assets/templates/`:

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
2. literature positioning still matches the actual draft
3. title, abstract, research questions, and contribution claims are aligned
4. all claims have evidence via 3-layer locator
5. anonymization is clean
6. supplementary validation is not overstated
7. discussion sentences can trace back to results
8. reviewer committee outputs do not contain unresolved desk-reject blockers
9. if a prose-risk pass is used, it follows `human_style_policy.md` and does not alter claims, citations, numeric meaning, or generalization boundary

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

Read from `references/` when you need:

- role definitions
- quickstart steps
- reusable protocol guidance

Use `assets/templates/` when creating a new paper workflow.
