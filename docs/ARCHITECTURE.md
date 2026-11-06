# Architecture — Eval Forge

## Flow
Evaluation manifest -> schema/provenance validation -> engine adapter -> task execution -> sample-level result store -> metric normalization -> paired/statistical analysis -> slice/failure analysis -> regression policy -> report/CI status.

## Modules
- `schemas/`: dataset, task, model, prompt, tool, evaluator, and run manifests.
- `adapters/`: Inspect, lm-eval, custom harnesses.
- `runner/`: orchestration, retries, deterministic settings.
- `results/`: per-sample outcomes, artifact references, errors.
- `statistics/`: bootstrap intervals, paired differences, effect sizes.
- `slices/`: domain/language/complexity and permitted dimensions.
- `policies/`: thresholds, minimum sample sizes, confidence requirements.
- `reports/`: Markdown/JSON/CSV and CI annotations.

## Run manifest
Record run ID, git SHA, dataset/task revision, model revision, prompt/template hash, tool/scorer versions, inference settings, seed, environment, timestamps, and cost/latency boundaries.

## Result record
Sample ID, input reference/hash, output reference, score(s), scorer metadata, latency/cost metadata, status, and structured error. Redact sensitive content or keep it in approved systems.

## Statistics
Prefer paired comparisons on identical samples. Bootstrap at the appropriate independent unit; report interval for the difference and effect size. State assumptions and avoid significance claims with inadequate samples.

## CI behavior
Support minimum coverage, absolute/relative thresholds, confidence/effect-size conditions, and explicit inconclusive state. Underpowered or noisy tests must not silently pass as “no regression.”
