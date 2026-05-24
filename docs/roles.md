# PaperForge Roles

## Topic Scoping Agent

- builds and narrows the topic funnel
- rejects tool-led but paper-weak ideas early
- locks the paper object, question, and survival criteria

## Literature Positioning Agent

- builds the scoping corpus
- organizes seed papers, themes, and gap candidates
- keeps a source inventory tied to actual writing use

## Problem Framing Agent

- fixes research questions, title, abstract, contribution logic
- ensures the paper is question-led rather than tool-led

## Data Governance Agent

- controls anonymization, publishable variables, restricted fields

## Methods and Statistics Agent

- fixes unit of analysis, comparison boundaries, robustness logic

## Results Agent

- organizes tables and figures
- does not interpret

## Interpretation Agent

- writes discussion
- must trace every claim back to evidence

## Venue Style Editor Agent

- reshapes language and section logic for the target venue

## Adversarial Reviewer Agent

- only attacks the draft
- surfaces blockers and major revision risks

## Concept Naming Agent

- triggered at Step 4.8, after motivation_lock and before claim_evidence_matrix
- generates 3 candidate sticky-concept names for the paper's main finding
- enforces naming constraints: noun phrase or acronym; 3-6 letter acronym preferred OR short reusable phrase; differentiating against prior literature; computable / measurable; motivation-aligned
- records the chosen name in `motivation_lock.md` field `sticky_concept`
- audit role: ensures the concept appears in title, abstract opener/closer, contribution sentence, and ≥ 5 times in body

## Methodology Spin-off Agent

- triggered at Step 6.4, after writing_rationale_matrix controlling framework is filled
- evaluates whether the paper's method itself merits a separate methods paper
- requires all of: ≥ 2 novel methodological components; cross-domain method value; distinct venue available for the method paper
- if all hold, records spin-off candidate in `notes/methodology_spinoff_candidates.md` with title / feeding components / target venue / decision date
- prevents the failure mode where method is buried in §3.2 of an application paper and never cited as a standalone contribution
