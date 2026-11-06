# Roadmap

## Phase 0 — Prior art and schema
- [ ] Compare Inspect, lm-eval, HELM, and CI evaluation systems.
- [ ] Define portable run/task/result schemas and privacy rules.
**Exit:** a clear integration-layer contribution.

## Phase 1 — Paired evaluation MVP
- [ ] Implement manifest validation.
- [ ] Integrate one existing evaluation engine.
- [ ] Store sample-level outcomes.
- [ ] Generate paired baseline/candidate report.
**Exit:** reproducible comparison on identical cases.

## Phase 2 — Statistical analysis
- [ ] Add paired bootstrap intervals and effect sizes.
- [ ] Add slice reports and minimum-sample warnings.
- [ ] Add evaluator disagreement analysis.
**Exit:** report distinguishes signal from noise.

## Phase 3 — Regression gates
- [ ] Add policy configuration and pass/fail/inconclusive states.
- [ ] Add CI output and second engine adapter.
**Exit:** safe, documented release gates.

## Phase 4 — Release
- [ ] Publish schema, adapter guide, synthetic example suite, and limitations.
- [ ] Seek external review.
