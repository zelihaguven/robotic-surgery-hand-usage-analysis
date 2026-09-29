# Robotic Surgery Hand Usage Analysis

**Deep Learning-Based Image Segmentation for Surgeon Hand Usage Analysis in Robotic Surgery**

 Department of Computer Engineering, Faculty of Engineering, Bursa Uludağ University (2026–2027 Fall Semester).

---

## Overview

Analyzing how a surgeon uses their hands and instruments in robotic surgery systems such as Da Vinci is important for performance assessment in surgical training. Today this assessment relies largely on observation and subjective judgment, and there is no standard, repeatable measurement method.

This project develops a system that automatically extracts surgeon left/right hand and instrument usage metrics from video data recorded in Da Vinci simulation and dry-lab environments. It uses a mask-based approach built on deep learning algorithms or Segment Anything (SAM)-like segmentation models.

## Objectives

- Extract instrument/hand masks from simulation video frames
- Compute the following metrics from the masks:
  - Left-right hand usage ratio
  - Path length
  - Collision
- Validate the computed metrics against the ground-truth values provided by the simulator
- Apply the validated model to performance assessment of surgical operations performed in a dry-lab environment

## Approach

```
Simulation / dry-lab video
        │
        ▼
Preprocessing (cleaning, frame extraction)
        │
        ▼
Segmentation (deep learning model or SAM-like model)
        │
        ▼
Instrument / hand masks
        │
        ▼
Metric extraction (usage ratio, path length, collision)
        │
        ▼
Comparison with simulator ground truth (MAE, RMSE, R²)
```

## Data

- **Training and validation:** Simulation data in which usage ratio, path length and collision values are known in advance (ground truth). Real surgical data is not used for training.
- **Application:** Video recorded during surgical operations in a dry-lab environment.

Datasets are not stored in this repository.

## Evaluation

The extracted metrics are compared with the simulator's reference values using regression metrics:

| Metric | Purpose |
|---|---|
| MAE | Mean absolute error between predicted and ground-truth values |
| RMSE | Error measure that penalizes large deviations |
| R² | Agreement between model outputs and ground truth |

### Success criteria

- Left-right hand usage ratio, path length and collision metrics can be computed from the segmentation outputs
- The metrics show low error against simulator ground truth (MAE, RMSE)
- Model outputs show high agreement with ground truth (R²)
- Results are consistent and repeatable across different simulation scenarios
- The model can be used for performance assessment of dry-lab surgical operations

## Roadmap

Progress is tracked with GitHub milestones and the project board.

| Milestone | Description |
|---|---|
| M0 – Project Setup | Project proposal, repository, tracking and reference management setup |
| M1 – Literature Review | Robotic surgery, image segmentation and surgical motion analysis literature |
| M2 – Simulation Data Acquisition | Obtaining simulation video data with known ground-truth metrics |
| M3 – Preprocessing | Video/image cleaning and frame extraction |
| M4 – Segmentation Model Development | Selecting a deep learning or SAM-like model and setting up the training pipeline |
| M5 – Training | Training on simulation data or fine-tuning SAM |
| M6 – Metric Extraction | Computing usage ratio, path length and collision from masks |
| M7 – Ground Truth Comparison | Evaluation against simulator reference values with MAE, RMSE, R² |
| M8 – Dry-lab Application | Testing the model on dry-lab surgical operations |
| M9 – Reporting | Final report, presentation and demo video |

## Tech Stack

- Python
- Image processing and segmentation libraries (to be finalized in M4)

## Status

🚧 In progress: M0 – Project Setup

## Author

**Zeliha Ilgın Güven**, Computer Engineering, Bursa Uludağ University

## Advisor

**Assoc. Prof. Dr. Murtaza Cicioğlu**
