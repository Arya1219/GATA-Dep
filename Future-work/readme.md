# DynDep: Dynamical Topology-Based Multimodal Depression Detection

## Overview
[cite_start]Existing multimodal depression detection systems primarily treat depression assessment as a static classification problem[cite: 5]. [cite_start]Audio, facial expressions, gaze, head pose, and behavioral signals are fused to predict a binary depression label[cite: 6]. [cite_start]While effective, such approaches largely ignore the temporal evolution of behavioral states throughout an interview[cite: 7]. 

[cite_start]In this work, we propose DynDep, a dynamical topology-based framework for multimodal depression detection[cite: 8]. [cite_start]Instead of viewing depression as a static collection of features, we model an interview as a latent behavioral trajectory evolving over time[cite: 9]. [cite_start]A multimodal encoder transforms sequential observations into latent states, producing a trajectory in behavioral state space[cite: 10].

## Key Contributions
* [cite_start]A trajectory-based formulation of depression detection[cite: 27].
* [cite_start]Recurrence-based behavioral biomarkers[cite: 28].
* [cite_start]Persistent homology biomarkers for latent behavioral trajectories[cite: 29].
* [cite_start]Topology-aware learning objectives for multimodal depression detection[cite: 30].
* [cite_start]An interpretable framework compatible with existing multimodal architectures[cite: 31].

## Methodology

### [cite_start]1. Latent Behavioral Trajectory [cite: 33]
[cite_start]Given multimodal observations over $T$ temporal windows, a multimodal encoder generates latent states[cite: 34]:
[cite_start]$$z_{1},z_{2},...,z_{T}$$ [cite: 35]
[cite_start]forming a continuous trajectory in the latent space[cite: 37].

### [cite_start]2. Recurrence Dynamics [cite: 38]
[cite_start]A recurrence matrix is constructed from pairwise latent-state distances[cite: 39]. From this matrix, we compute:
* [cite_start]**Recurrence Rate:** The density of recurrence points in the matrix[cite: 40].
* [cite_start]**Determinism:** The predictability of the system based on diagonal lines[cite: 41].
* [cite_start]**Laminarity:** The occurrence of laminar states based on vertical lines[cite: 42].
* [cite_start]**Recurrence Entropy:** The complexity of the deterministic behavior[cite: 43].

### [cite_start]3. Persistent Homology [cite: 45]
[cite_start]Persistent homology is applied directly to the latent trajectory to extract structural invariants[cite: 46]. Topological biomarkers include:
* [cite_start]**Betti-0 ($\beta_{0}$):** Represents trajectory fragmentation[cite: 47].
* **Betti-1 ($\beta_{1}$):** Measures cyclic behavior and looping dynamics[cite: 48].
* **Persistence Entropy:** Quantifies the distribution of topological feature lifetimes[cite: 49].
* [cite_start]**Average Persistence Lifetime:** Measures the robustness of the discovered topological structures[cite: 50].

### 4. Dynamical Stability & Topology-Aware Learning
[cite_start]Temporal smoothness is measured through trajectory velocity and acceleration statistics[cite: 53]. [cite_start]A dedicated smoothness regularizer encourages realistic, non-erratic behavioral evolution across time steps[cite: 54]. [cite_start]The final composite optimization objective is defined as[cite: 57]:
[cite_start]$$L=L_{cls}+\lambda_{1}L_{smooth}+\lambda_{2}L_{topo}$$ [cite: 58]
[cite_start]where $L_{cls}$ denotes the standard classification loss, $L_{smooth}$ promotes temporal consistency, and $L_{topo}$ preserves meaningful global trajectory structure[cite: 60].

## Experimental Design
[cite_start]**Dataset & Modalities:** We evaluate our framework on the benchmark DAIC-WOZ dataset[cite: 63]. [cite_start]The multimodal input space incorporates audio features, Facial Action Units (AUs), 2D/3D Facial Landmarks, gaze vectors, and head pose metrics[cite: 64, 65, 66, 67, 68].

[cite_start]**Baselines & Integration:** The proposed model is compared against standard paradigms including Early Fusion, Transformer Fusion, and GATA-Dep[cite: 70, 71, 72, 73]. [cite_start]We further demonstrate that the proposed framework can operate as a plug-in extension to existing multimodal architectures, including transformer-based systems such as GATA-Dep[cite: 16, 75].

## Expected Impact
[cite_start]The proposed framework shifts the paradigm of automated depression detection from static classification toward dynamical behavioral modeling[cite: 83]. [cite_start]It provides highly interpretable biomarkers describing how behavioral states evolve during clinical interviews, offering a critical bridge between machine learning representations and established psychological theory[cite: 84].

## Research Report
For full details on the methodology, theoretical analysis, and evaluation metrics, please refer to the core report:
[cite_start]📄 [`DYN_Dep_Idea.pdf`](./DYN_Dep_Idea.pdf) [cite: 2] [cite_start](Dated: June 20, 2026 [cite: 3])
