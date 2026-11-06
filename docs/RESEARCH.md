# Research brief — Eval Forge

## Problem
Evaluation outcomes depend on task definitions, dataset versions, prompts, model revisions, tools, scoring code, and randomness. Without provenance and statistical analysis, teams can mistake noise for progress or hide regressions in slices.

## Prior art
Study HELM, EleutherAI lm-evaluation-harness, Inspect AI, OpenAI Evals patterns, and application-specific test suites. Do not rebuild every evaluator. The intended contribution is a portable experiment/provenance layer with paired statistical analysis and actionable regression policies. This should complement, not duplicate, RAG-specific evaluation in RagFabric.

## Questions and hypotheses
Are apparent score changes robust under paired comparisons? Which slices regress while aggregate metrics improve? How sensitive are outcomes to prompt, sampling, tool, and evaluator versions? H1: paired sample-level comparisons are more informative than unrelated aggregate means; H2: intervals/effect sizes reduce false improvement claims; H3: slice analysis exposes hidden regressions.

## Method
Freeze task/dataset versions; record model, prompt, tool, evaluator and seed; run baseline and candidate on matched cases; preserve per-sample outcomes; use paired bootstrap or suitable tests; report confidence intervals, effect sizes, sample sizes, and multiple-comparison caveats; predefine primary metrics and thresholds.

## Metrics
Exact match, accuracy, F1, pass rate, latency, cost, safety-policy outcomes, tool success, task completion, and rubric/judge scores. Version metric definitions. Do not combine incomparable metrics into an opaque composite score.

## LLM-as-judge safeguards
Use explicit rubrics, blinded ordering where possible, calibration against human-reviewed examples, agreement/disagreement analysis, and recorded judge prompt/model revisions. Judge scores are measurements with error, not ground truth.

## References
- HELM: https://crfm.stanford.edu/helm/
- lm-evaluation-harness: https://github.com/EleutherAI/lm-evaluation-harness
- Inspect AI: https://github.com/UKGovernmentBEIS/inspect_ai
- SciPy statistics: https://docs.scipy.org/doc/scipy/reference/stats.html
- Hugging Face Evaluate: https://github.com/huggingface/evaluate
