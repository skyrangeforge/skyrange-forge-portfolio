# Case study: preserving evaluation integrity

Eric directed agents carrying out evaluations and corrective audits; he owned the requirements, QC and acceptance decisions. No claim is made that he manually implemented or independently reran every check.

## Why this matters

A local model replacement is useful only if the comparison measures the intended capability. Tool access, answer leakage, parsing, time budgets, sampling and fallback behavior can produce convincing but invalid headline scores. (Based on private evaluation reports and the reference-run audit.)

## Contaminated reference run

An earlier partial mapper run used tools, and in many of those cases the solver successfully read answer fixtures. The expected patch for the exact question could therefore enter the solver's context.

That partial run was invalidated for semantic comparison. Artifacts were retained rather than erased, and the coordinator stopped continuing the invalid pass. A fresh closed-book full pass used isolated per-request workspaces, a no-tools contract, identity checks and stream auditing.

The clean pass completed with zero tool events. Exact score breakdowns are withheld from this public copy. No reply repair or failed-row retry was used in that clean mapper pass.

## Fairness limits retained

Local mapper calls and the clean external reference used different time limits. Concurrency and system prompts also differed. CLI token/timing metadata are not equivalent to raw endpoint measurements. The audit removes tool-based leakage; it does not make the harnesses identical or create repeated-trial confidence intervals.

## Routing experiment: promising efficiency signal, rejected replacement

A separate DeepSeek experiment evaluated retrieval, validation and selective escalation. Routing criteria, prompts and implementation details are withheld.

The routed arm sent a share of evaluation cases to an external model. That share is a call-count statistic, not a measured dollar-saving percentage. Relative to validated local output, routing improved some exact-match counts but also increased some unsafe outputs, and agreement on a held-out review subset did not improve despite more cases being resolved.

The original baseline's time limit differed from the follow-up budget; fewer timeouts in a newer arm must not be marketed as an isolated reliability gain. Valid final JSON is accepted pipeline output, not proof of native constrained decoding or semantic safety.

**Decision:** no production replacement. The side pipeline needed better semantic coverage, calibrated escalation, independent untouched-job evaluation, packaging and an explicit future deployment decision.

## Practices worth demonstrating

- Freeze questions, graders and hidden answers before the run.
- Prevent the model from reading the answer source; audit actual tool events.
- Verify actual model identity, not a requested label.
- Keep failed, contaminated and infrastructure-invalid artifacts with reasons.
- Distinguish raw model scores from deterministic fallback scores.
- Report clean completion separately from artifact correctness at timeout.
- Keep precision/unsafe behavior alongside accuracy and throughput.
- Preserve negative conclusions even when they weaken the sales story.
- Use call-count routing statistics as call-count statistics, not fabricated cost savings.

This work supports an evaluation-engineering portfolio claim, not a claim of general frontier-model parity.
