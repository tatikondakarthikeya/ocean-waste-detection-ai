# Review notes — Ocean Waste Detection and Classification

Review performed against the staged notebook source on 2026-10-14. This is a static source review; the notebook was not executed end-to-end.

## Findings

1. **Invalid mAP proxy (high):** one custom Faster R-CNN cell computes `mAP@0.5 = precision * recall / 100`. This is not mean average precision. The reviewed notebook cell now prints a warning instead of reporting this value.
2. **Manually entered metrics (high):** comparison tables in cells 63, 65, 66, and 74 include hard-coded values. These are retained for traceability but now have visible warning cells and must not be treated as verified experimental results.
3. **Custom evaluator needs correction (high):** the fast evaluator only checks a limited number of batches and its TP/FN matching/counting logic is not a robust one-to-one detection matcher. Do not report its metrics until corrected and validated against a standard evaluator.
4. **Heuristic toxicity/priority (high):** toxicity numbers and cleanup priorities are manually assigned mappings, not measured toxicological properties or validated environmental-risk scores.
5. **Reproducibility (medium):** paths target Kaggle; dependencies are unpinned; multiple detection/classification experiments are combined; exact seeds, split methodology, and checkpoints need documentation.
6. **Provenance/license (release blocker):** dataset source/citation/license and code licensing remain unverified.

## Recommended interpretation

Treat this as an experimental notebook collection. Do not claim 99.28% precision, 99.24% recall, 98.74% mAP, or classification metrics as verified results until the exact evaluation procedure is rerun from checkpoints on the documented test set and output logs are retained.
