# Keypoint Detection and Matching

Local feature detection and description, spatial keypoint-distribution analysis, brute-force and nearest-neighbour matching, and robustness tests under image transformations.

**Status: source implementations included.** Notebooks may need local input data and configuration to run.

## What this covers

- Harris corners and available OpenCV feature detectors
- Descriptor extraction and nearest-neighbour matching
- Grid-based keypoint counts
- Blur, rotation and Gaussian-noise experiments

## Processing pipeline

~~~mermaid
flowchart LR
    A[Original image] --> B[Detect keypoints]
    A --> C[Blur / rotate / add noise]
    C --> D[Detect keypoints again]
    B --> E[Compute descriptors]
    D --> F[Compute descriptors]
    E --> G[Match and score]
    F --> G
~~~

## Technical explanation

Harris corner response: **R = det(M) − k · trace(M)²**, where M is a local second-moment matrix; strong positive responses indicate corner-like structures.

## Contents

- `notebooks/keypoint-detection-and-matching.ipynb` — from `week04_histogram_processing/lab04_histogram_processing.ipynb`

## Getting started

Use Python 3.10+ in a virtual environment:

~~~bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
~~~

On Windows, activate with `.venv\Scripts\activate` instead. Install `jupyterlab` if it is not installed already. Open a notebook under `notebooks/`. Dataset/model paths in the original examples may need updating.

## Important limitations

Available detectors depend on your OpenCV build. The source notebook references local input images; update the image path. Results are not independently benchmarked.

Input assets, lecture handouts, PDFs, trained models, cached results and third-party datasets have intentionally not been republished. Notebook code and explanatory cells are retained, while saved cell outputs are removed. No performance claims or additional experiments have been invented.

## Provenance

Adapted from the publicly available [ComputerVision source collection](https://github.com/dbxdrgsl/ComputerVision). Source-to-destination file mappings appear above. Each repository is organized by technical subject rather than course numbering.
