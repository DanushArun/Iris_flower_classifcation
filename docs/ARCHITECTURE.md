# Iris Classification — Architecture and implementation

This guide follows the tracked implementation. Proposed work is identified separately.

## The problem and the system boundary

Iris flower measurements provide an approachable way to inspect the relationship between inputs
and Species. This repository keeps that work in a notebook so preparation, computation and saved
outputs can be read together. Its value is an inspectable experiment, not a deployed prediction
service.

## Processing path

```mermaid
flowchart LR
    N0["Measurements"]
    N1["split"]
    N2["tree"]
    N3["confusion matrix"]
    N0 --> N1
    N1 --> N2
    N2 --> N3
```

## End-to-end behavior

### 1. Supply the input data

The required CSV files are not tracked. Obtain an authorized copy with the expected schema and
replace the author-specific absolute paths before execution.

### 2. Inspect the preparation

Import cells appear after first use and must run first in a clean kernel. Review the
transformations and exclusions before rerunning; an output cannot be understood separately from
its input preparation.

### 3. Run the experiment

The implemented method is DecisionTreeClassifier. The tree has no fixed random seed. Execute in a
fresh kernel to reveal ordering and dependency problems.

### 4. Read the diagnostics

The saved confusion matrix records 30/30 correct on one historical holdout. That is one small
split, not a generalization guarantee. The identifier column is excluded from predictive features.

## Design choices and consequences

### Inputs are explicit

SepalLengthCm, SepalWidthCm, PetalLengthCm, PetalWidthCm.

### Method is inspectable

DecisionTreeClassifier is the implemented method; no broader modeling capability is inferred.

### Historical evidence is labeled

The saved confusion matrix records 30/30 correct on one historical holdout. That is one small
split, not a generalization guarantee.

## Source entry points

### [Task_1.ipynb](../Task_1.ipynb)

18 nonempty Python cells are committed, along with any saved outputs.
Cell order and absolute data paths are part of reproducibility; outputs are historical.

## Implementation state

| State | Evidence boundary |
| --- | --- |
| Present | Notebook source and historical saved outputs |
| Required externally | Authorized CSV input and compatible Python packages |
| Not rerun | Data-dependent execution in this documentation pass |
| Not supplied | Deployment service, model registry or automated behavior suite |

“Present” means tracked source or assets exist. It does not mean a production or domain
validation has passed. See [Evaluation](EVALUATION.md) for reproducible checks and limits.
