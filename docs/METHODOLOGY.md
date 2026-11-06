# Evaluation methodology

## Before a run
Define primary metrics, slices and regression thresholds. Freeze task/dataset/evaluator versions. Pin model, prompt, tool and generation settings. Choose paired sample IDs and seeds. Define cost/latency boundaries.

## After a run
Validate sample coverage and failures. Compare baseline and candidate on matched cases. Report distributions, paired differences, bootstrap confidence intervals and effect sizes. Analyze slices and error categories. Preserve sample-level results subject to privacy rules.

## Regression states
- **Pass:** adequate coverage and no meaningful regression beyond configured threshold.
- **Fail:** evidence of regression beyond threshold.
- **Inconclusive:** insufficient samples, high variance, missing baseline or invalid run.
Inconclusive must never silently become pass.

## Human review
Prioritize large disagreements, judge disagreement, safety impact and high-value cases. Record reviewer instructions and adjudication rules.