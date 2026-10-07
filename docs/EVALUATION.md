# Iris Classification — Evaluation guide

Start with the smallest path that exercises the project. Distinguish source inspection,
syntax/build checks, functional behavior and domain validation when recording a result.

## Guided reading and demonstration

1. **Supply the input data.** The required CSV files are not tracked. Obtain an authorized copy
with the expected schema and replace the author-specific absolute paths before execution.

2. **Inspect the preparation.** Import cells appear after first use and must run first in a clean
kernel. Review the transformations and exclusions before rerunning; an output cannot be understood
separately from its input preparation.

3. **Run the experiment.** The implemented method is DecisionTreeClassifier. The tree has no fixed
random seed. Execute in a fresh kernel to reveal ordering and dependency problems.

4. **Read the diagnostics.** The saved confusion matrix records 30/30 correct on one historical
holdout. That is one small split, not a generalization guarantee. The identifier column is
excluded from predictive features.

## Declared checks

These commands/checks describe the intended verification path. Their presence in this
guide does not claim that they passed. See the dated evidence below and the README for setup.

```text
Parse notebook JSON and nonempty Python cells without execution.
```

## Evidence levels

| Level | What it establishes | What it does not establish |
| --- | --- | --- |
| Source review | A path exists in tracked code | Successful runtime behavior |
| Syntax/build | Parser/compiler accepts that path | End-to-end correctness |
| Behavioral check | A specific input/output case passed | Generalization beyond cases |
| Domain evaluation | Performance on a stated target setting | Other users/data/environments |

## What to record

- Commit, environment, dependency versions and date.
- Input provenance and whether data is synthetic, public or privately supplied.
- Absolute pass/fail/skip counts; keep failed cases and their root causes.
- Whether external services, hardware or a production deployment were actually exercised.
- Expected output and an artifact showing the observation.

## Review scenarios

- **Inputs are explicit:** SepalLengthCm, SepalWidthCm, PetalLengthCm, PetalWidthCm.

- **Method is inspectable:** DecisionTreeClassifier is the implemented method; no broader modeling
capability is inferred.

- **Historical evidence is labeled:** The saved confusion matrix records 30/30 correct on one
historical holdout. That is one small split, not a generalization guarantee.

## Documentation inspection — 7 October 2026

The documentation was traced to committed source and checked for local links, balanced
code fences and supported implementation claims. Historical notebook outputs remain labeled
as historical. Live provider access, private databases and hardware behavior are not inferred
from configuration or dependency files. Any fresh run is recorded separately in the README.

## Next evidence to collect

- Supply data provenance and a reproducible local path.
- Record a fresh-kernel run with package versions.
- Evaluate stability across independent samples before widening any performance claim.
