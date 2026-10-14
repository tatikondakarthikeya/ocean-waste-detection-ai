# Ocean Waste Detection and Classification

A research notebook exploring object detection and waste-category classification for marine imagery. Experiments include Faster R-CNN, YOLO/Ultralytics, RT-DETR, CNN classifiers, and an EfficientNet-B0 + multi-head self-attention (MHSA) experiment, alongside a heuristic cleanup-priority demonstration.

> **Research status: draft / results not independently reproduced.** Keep this repository private until the dataset provenance, evaluation code, and manually entered metric tables have been reviewed.

## Contents

- `notebooks/ocean_waste_detection.ipynb` — combined detection/classification experiments and exploratory analysis.
- `data/README.md` — dataset provenance and setup checklist.
- `requirements.txt` — Python dependencies; PyTorch/CUDA compatibility depends on platform.

## Setup

The notebook was authored for Kaggle paths. Use an isolated environment and install a PyTorch build compatible with your OS, Python version, and hardware before installing the remaining packages:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

The dependency list is currently unpinned and is not a reproducible lockfile. Notebook cells also use inline `!pip install` commands; consolidate and pin dependencies before a reproducible public release.

## Run

1. Obtain the dataset from its original authorized source and confirm its license and label format.
2. Update `/kaggle/input/ocean-waste-detection` paths for your environment.
3. Run cells in order, verifying data YAML, label IDs, class names, and model output shapes.
4. Use a held-out test split for final reporting; do not select hyperparameters using the test split.
5. Record exact versions, seeds, split definitions, and checkpoint-selection rules.

## Evaluation warnings

- The notebook includes multiple experimental approaches and repeated training/evaluation cells. These are not yet a single clean pipeline.
- One custom Faster R-CNN evaluation cell computes `mAP@0.5` as `precision * recall / 100`. **This is not a valid mAP calculation** and has been changed in this review patch to an explicit warning. Use a correct detection metric implementation instead.
- Several comparison tables in the notebook contain manually specified metric values rather than values wired to the immediately preceding model evaluation. They are now marked as **unverified reference values**; do not cite them as measured results until reproduced.
- The custom fast evaluator only inspects a limited number of batches and its matching/counting logic requires correction and validation before any metric is reported.
- The toxicity/severity/priority mappings are heuristic illustrative values. They are not toxicological measurements, environmental-risk validation, or professional cleanup advice.

## Dataset, citation, and license

**Not yet complete.** Add the exact dataset title, source URL, version, citation, and license/terms after verifying them. Do not redistribute data unless the license explicitly permits it. No project license is asserted by this draft; choose one only after confirming code ownership and third-party terms.

## Public-release checklist

- [ ] Add verified dataset source, citation, version, and license/terms.
- [ ] Fix and test detection metric matching logic; use a standard evaluator for mAP.
- [ ] Reproduce every reported result from saved evaluation outputs/checkpoints.
- [ ] Replace manually entered comparison tables with computed results or remove them.
- [ ] Separate detection, classification, and heuristic prioritization into clear sections or notebooks.
- [ ] Pin dependencies and document tested hardware/software.
- [ ] Add an appropriate license only after rights review.
