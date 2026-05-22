# Revision Gate

> Revision gate 检查"是否好 / 是否完整"（内容层）。
> 形式层"是否真"由 `integrity_gate.md` 负责，且必须先通过。

## 前置门

- `failure_mode_checklist.md` 已填，7 模式均为 CLEAR 或显式 ACCEPTED_RISK
- `integrity_gate.md` 总判定 PASS
- 若两者未通过，本表不允许签出

## Blockers

### Blocker 0

Topic, question, and scope must remain locked. No silent drift.

### Blocker 1

Title, abstract, research question, and contributions must align.

### Blocker 2

Every major claim must map to explicit evidence via 3-layer locator in `claim_evidence_matrix.md`.

### Blocker 3

Anonymization and publishability checks must pass.

### Blocker 4

Discussion claims must trace back to results.

### Blocker 5

Literature positioning and claimed gap must still match the actual draft and cited sources.

### Blocker 6

Reviewer committee outputs (if used) contain no unresolved desk-reject blockers.

### Blocker 7

Prose-risk pass (if used) followed `human_style_policy.md`: no claim / citation / number / scope mutation; no detector-evasion intent.

## Major Risks

1.
2.
3.

## Sign-Off

- Integrity gate pass date:
- Failure mode checklist clear date:
- Revision gate signer:
- Date:
