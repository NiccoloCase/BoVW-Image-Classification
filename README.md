# 🧠 Bag of Visual Words for Image Classification

> Implementation and analysis of a **Bag of Visual Words (BoVW)** model for image classification, comparing **SIFT** and **ORB** feature detectors combined with **k-means** clustering and **SVM** classification.

---

## 📘 Overview

This repository contains the source code and analysis supporting the report:

> _"Bag of Visual Words for Image Classification: A Comparison Between SIFT and ORB Feature Detectors"_  
> by **Niccolò Caselli**, Politecnico di Milano.

The project explores how different feature extraction methods and clustering parameters affect the classification performance of the BoVW pipeline.

---

## ⚙️ Methodology

The BoVW pipeline implemented includes the following stages:

1. **Feature Extraction** — SIFT or ORB keypoints and descriptors.
2. **Visual Vocabulary Construction** — k-means clustering to form visual words.
3. **Feature Representation** — histograms of visual word occurrences.
4. **Classification** — Support Vector Machine (SVM) with linear or RBF kernel.

---

## 🧩 Architecture Diagram

<p align="center">
  <img src="figures/pipeline.png" width="700" alt="BoVW pipeline diagram"/>
</p>

---

## 📊 Results

### Quantitative Evaluation

| Feature Detector | Clusters | Kernel | mAP (%)  |
| ---------------- | -------- | ------ | -------- |
| SIFT             | 1500     | RBF    | **89.7** |
| ORB              | 1500     | RBF    | 78.2     |
| SIFT             | 1000     | Linear | 83.4     |

<p align="center">
  <img src="figures/mAP_vs_clusters.png" width="600" alt="mAP vs Clusters"/>
</p>

---

### Qualitative Evaluation

#### SIFT

<p align="center">
  <img src="figures/qualitative_sift.png" width="700" alt="SIFT qualitative results"/>
</p>

#### ORB

<p align="center">
  <img src="figures/qualitative_orb.png" width="700" alt="ORB qualitative results"/>
</p>

#### Mean Histograms

<p align="center">
  <img src="figures/mean_histograms.png" width="700" alt="Mean histograms per class"/>
</p>

---

## 🧠 Key Findings

- **SIFT** produces more distinctive and stable keypoints than ORB.
- The **RBF kernel** consistently outperforms the linear kernel in classification tasks.
- Increasing the number of clusters up to around **1500 visual words** improves mAP before plateauing.
- **ORB** struggles at smaller image scales and benefits from upscaling.
