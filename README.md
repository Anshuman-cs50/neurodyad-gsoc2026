# NeuroDyads EEG Analysis — GSoC 2026 Pre-Task
**ML4Sci | Brain-to-Brain Decoder: Validating Neural Synchrony Patterns in Human Conversation**

## Overview
This repository contains my pre-task submission for the NeuroDyads project at ML4Sci GSoC 2026.
The notebook implements a complete EEG hyperscanning analysis pipeline on a single conversational
dyad (NT#9-Listen / NT#10-speak), from raw EDF preprocessing through CEBRA contrastive embedding
to interpretation and extended analyses.

## Contents
| File | Description |
|---|---|
| `neurodyad_pretask_final.ipynb` | Complete solution — all 4 parts + 3 extensions |

## What the Notebook Covers
- **Part 1** — EDF loading, DIN1 marker segmentation, VREF removal, ICA artifact rejection
- **Part 2** — T×128 joint matrix construction, CEBRA training, KNN decoding (1.000), GoF (0.817), shuffled-label control
- **Part 3** — Embedding geometry interpretation, control analysis
- **Part 4** — Temporal confounding as core limitation; leave-one-dyad-out CV as proposed fix
- **Extension 1** — Frequency-band power comparison (delta/theta/alpha/beta/gamma) by condition
- **Extension 2** — Neural state trajectory visualisation within each segment
- **Extension 3** — Cross-entropy distance metric between embedding distributions (Roca et al., 2023)

## Requirements
```bash
pip install mne cebra scikit-learn numpy scipy matplotlib
```

## Key Results
| Metric | Main | Shuffled Control |
|---|---|---|
| KNN Decoding Accuracy | 1.000 ± 0.000 | 0.730 ± 0.003 |
| Goodness-of-Fit | 0.8173 | ≈ 0.000 |

## Environment
- Python 3.12 · MNE 1.11.0 · CEBRA 0.6.0 · PyTorch 2.10.0 · NumPy 2.0.2
