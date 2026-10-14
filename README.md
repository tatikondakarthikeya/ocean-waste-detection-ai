# Ocean Waste Detection and Classification

Research notebook exploring object detection and waste-category classification for ocean/marine waste, including Faster R-CNN, YOLOv8 and RT-DETR experiments, CNN classifiers, an EfficientNet-B0 + MHSA experiment, and a heuristic toxicity/severity/cleanup-priority mapping.

> **Status:** Research notebook draft. Results and code paths have not been independently reproduced during repository preparation.

## Contents
- `notebooks/ocean_waste_detection.ipynb` — original notebook with execution outputs removed; code cells are preserved.
- `data/README.md` — dataset setup guidance.

## Setup
Use a Python environment compatible with your installed PyTorch build and hardware. For GPU training, install the appropriate PyTorch/CUDA version from the official PyTorch instructions first, then install other dependencies:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Run
1. Obtain the dataset from its authorized source and verify its license.
2. Update `/kaggle/input/ocean-waste-detection` paths to match your environment.
3. Run cells in order; confirm label formats and model output shapes before training.
4. Recompute evaluation metrics on a held-out test set before reporting results.

## Important research caveats
- The notebook includes multiple experimental approaches and repeated training/evaluation cells; refactor into clearly separated detection and classification experiments before public release.
- The toxicity values and severity/priority mapping are heuristic values defined in the notebook, not a validated toxicological assessment. Do not present them as scientifically validated toxicity measurements.
- Some metric tables are manually specified in notebook cells. Reproduce results from actual model evaluation before citing them.
- Dataset, weights, and generated artifacts are excluded.

## Data, citation and license
Add the dataset source, citation and license. Add a project license only after confirming the rights to publish the code.
