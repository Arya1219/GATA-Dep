
```markdown
# GATA-Dep: Gender-Aware Temporal Alignment for Multimodal Depression Detection

## Overview
**GATA-Dep** is a multimodal deep learning framework for depression detection from clinical interviews. The model introduces a Gender-Aware Temporal Alignment (GATA) module that learns modality-specific temporal offsets and gender-conditioned alignment weights to better capture asynchronous behavioral signals across multiple modalities.

The framework is evaluated on the DAIC-WOZ benchmark and integrates audio, facial action units, facial landmarks, gaze features, and head pose signals within a transformer-based architecture.

## Motivation
Human behavioral cues are rarely synchronized. 

In depression assessment interviews, vocal changes, facial expressions, gaze shifts, and head movements often occur with temporal delays relative to one another. Most multimodal fusion methods assume perfect synchronization and therefore may fail to capture these delayed interactions.

GATA-Dep addresses this challenge by learning temporal alignments directly from data instead of assuming fixed synchronization.

## Key Contributions
* Introduced Gender-Aware Temporal Alignment (GATA) for multimodal behavioral modeling.
* Learned temporal offsets within a window of ±K frames.
* Incorporated gender-conditioned alignment distributions.
* Developed a transformer-based multimodal fusion framework.
* Performed participant-level depression prediction.
* Conducted ablation studies on:
  * Temporal offset range
  * Gender conditioning
  * Missing-modality robustness
* Analyzed interpretability through learned temporal offset distributions.
* Provided theoretical analysis linking temporal alignment to information preservation.

## Architecture

![GATA-Dep Architecture](figures/architecture.png.jpeg)
*Figure 1: Overall architecture of the GATA-Dep framework.*

![GATA Module](figures/gata_module.png)
*Figure 2: Detailed view of the Gender-Aware Temporal Alignment (GATA) module.*

**Pipeline:**

```text
Audio Features (79D)
Action Units (20D)
Facial Landmarks (204D)
Gaze Features (12D)
Head Pose Features (6D)

        ↓

Modality-Specific Encoders

        ↓

Gender-Aware Temporal Alignment (GATA)

        ↓

Transformer Encoder

        ↓

Participant-Level Aggregation

        ↓

Depression Classification

```

## Dataset

### DAIC-WOZ

The model is evaluated on the DAIC-WOZ depression benchmark.

**Modalities used:**

| Modality | Dimension |
| --- | --- |
| Audio | 79 |
| Action Units | 20 |
| Facial Landmarks | 204 |
| Gaze | 12 |
| Head Pose | 6 |

## Model Configuration

| Component | Value |
| --- | --- |
| Hidden Dimension | 256 |
| Transformer Layers | 2 |
| Attention Heads | 8 |
| Dropout | 0.1 |
| Temporal Window | K = 12 |
| Optimizer | AdamW |
| Mixed Precision | Enabled |
| Evaluation | Participant-Level |

## Repository Structure

```text
GATA-Dep/
│
├── GATA_Dep_final.ipynb
├── paper/
│   └── GATA_Dep_Draft.pdf
│
├── figures/
│   ├── architecture.png.jpeg
│   └── gata_module.png
│
├── requirements.txt
├── README.md
└── .gitignore

```

## Experiments

The repository contains implementations for:

* Full GATA-Dep model
* Baseline multimodal fusion model
* Gender ablation studies
* Temporal offset ablation studies
* Missing-modality robustness analysis
* Participant-level evaluation

## Results

The proposed framework demonstrates strong participant-level depression detection performance while providing interpretable temporal alignment distributions and robust multimodal fusion.

Complete experimental details are available in the accompanying paper.

## Research Paper

A full research manuscript describing the methodology, theoretical analysis, experimental setup, and ablation studies is included in:

[`paper/GATA_Dep_Draft.pdf`](https://www.google.com/search?q=paper/GATA_Dep_Draft.pdf)

## Author

**Arya Giri** Integrated Dual Degree (Biomedical Engineering)

Indian Institute of Technology (BHU), Varanasi

## Citation

```bibtex
@article{giri2025gatadep,
  title={GATA-Dep: Gender-Aware Temporal Alignment for Multimodal Depression Detection},
  author={Giri, Arya},
  year={2025}
}

```

```

```
