# Eval Forge

**A reproducible evaluation and regression-testing layer for AI systems, models, and agent workflows.**

Eval Forge focuses on the reliability of evaluation: versioned tasks and datasets, paired comparisons, statistical uncertainty, slice analysis, prompt/config provenance, and regression policies. It complements existing evaluation engines rather than replacing them.

## Problem
Scores change with prompts, model versions, sampling settings, dataset revisions, evaluator changes, and randomness. Aggregate scores can hide severe regressions in important slices.

## Proposed contribution
- Immutable evaluation manifests and provenance.
- Dataset/task versioning.
- Paired sample-level comparisons.
- Bootstrap confidence intervals and effect sizes.
- Slice and failure analysis.
- Prompt/model/tool/config lineage.
- Regression gates with pass/fail/inconclusive states.

## Integrations to investigate
Inspect AI, EleutherAI lm-evaluation-harness, HELM, and custom application/agent test suites. Reuse established task definitions. This project is not a universal intelligence score or a replacement for every harness.

## Documentation
- [Research brief](docs/RESEARCH.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Methodology](docs/METHODOLOGY.md)
- [Roadmap](docs/ROADMAP.md)

## Status
Research/design phase. No benchmark scores or rankings are claimed until reproducible runs are available.

## Principles
Freeze versions, preserve sample-level results safely, report uncertainty and sample counts, calibrate LLM-as-judge scoring against human review, and avoid opaque composite metrics.

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.