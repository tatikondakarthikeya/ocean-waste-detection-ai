# Dataset setup and provenance

No dataset is included in this repository.

Before running the notebook, record the dataset's exact title, original source URL, version/download date, citation, and license/terms here. Verify that redistribution of images and annotations is permitted before adding any data to Git.

The current notebook expects a YOLO-style layout similar to:

```text
<dataset-root>/
  data.yaml
  train/images/   train/labels/
  valid/images/   valid/labels/
  test/images/    test/labels/
```

Confirm that `data.yaml` class names and numeric class IDs match the notebook's `CLASS_NAMES` and toxicity-map keys. The toxicity map is a heuristic demonstration, not validated toxicology.
