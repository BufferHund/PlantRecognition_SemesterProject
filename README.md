

# Plant Recognition – CNN Architectures & Transfer Learning

This repository contains four experiments evaluating the effects of model architecture, dataset scale, and transfer learning strategies on plant species recognition. The code for each experiment is hosted in Kaggle notebooks (links below).

---

## Overview

We compare three CNN architectures—CustomCNN-S, ResNet-18, and ConvNeXt-Tiny—across different datasets and pretraining strategies to understand how capacity and data scale influence performance in fine-grained classification tasks.

---

## Experiments

### 1. Small-Scale Dataset Benchmarking

* **Dataset:** [Plant Seedlings Classification](https://www.kaggle.com/competitions/plant-seedlings-classification)
* **Notebook:** [Experiment 1 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp1)
* **Result:** Pretrained ResNet-18 achieved 97.7% accuracy. ConvNeXt-Tiny trained from scratch failed to converge.
* **Insight:** Pretrained classic architectures are more effective on small datasets than high-capacity models trained from scratch.

### 2. Large-Scale Dataset Generalization

* **Dataset:** [LeafSnap Dataset](https://www.kaggle.com/datasets/xhlulu/leafsnap-dataset)
* **Notebook:** [Experiment 2 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp2)
* **Result:** ConvNeXt-Tiny surpassed ResNet-18 (F1 = 0.979 vs 0.965).
* **Insight:** High-capacity models benefit from larger and more diverse datasets, capturing finer visual patterns.

### 3. In-Domain vs. Generic Transfer Learning

* **Datasets:**

  * Pretraining: [LeafSnap Dataset](https://www.kaggle.com/datasets/xhlulu/leafsnap-dataset)
  * Target: [Plant Seedlings Classification](https://www.kaggle.com/competitions/plant-seedlings-classification)
* **Notebook:** [Experiment 3 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp3)
* **Result:** Full fine-tuning outperformed gradual unfreezing (F1 = 0.978 vs 0.910).
* **Insight:** In-domain pretraining combined with full fine-tuning provides a stronger initialization than ImageNet pretraining.

### 4. Large-Scale Noisy Pretraining

* **Datasets:**

  * Pretraining: [iNaturalist Plant Subset](https://www.kaggle.com/datasets/zackr67/inaturalist)
  * Target: [Plant Seedlings Classification](https://www.kaggle.com/competitions/plant-seedlings-classification)
  * Pretrained weights (optional): [iNaturalist Pretrained Weights](https://www.kaggle.com/datasets/zackr67/inatweight)
* **Notebook:** [Experiment 4 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp4)
* **Result:** Achieved F1 = 0.965 with full fine-tuning, outperforming gradual unfreezing.
* **Insight:** Large-scale, diverse pretraining can match or approach in-domain performance when fully fine-tuned.

---

## Conclusions

* Small datasets: Pretrained ResNet-18 offers stable, high accuracy.
* Large datasets: ConvNeXt-Tiny leverages scale for superior performance.
* Transfer learning: Full fine-tuning consistently outperforms gradual unfreezing; in-domain or large diverse pretraining provides the best starting point.

---

## Code Notebooks

* [Experiment 1 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp1)
* [Experiment 2 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp2)
* [Experiment 3 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp3)
* [Experiment 4 – Kaggle](https://www.kaggle.com/code/zackr67/nn-exp4)

---

## Future Work

* Explore ensemble methods combining ResNet-18 and ConvNeXt-Tiny.
* Evaluate attention-based part localization or metric learning for improved fine-grained classification.