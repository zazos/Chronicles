---
tags: thesis
---

# Understanding ROC-AUC and PR-AUC for Music Mood Classification

Music mood classification on datasets involving multilabel tagging with inherent class imbalance, where certain moods (e.g., “calm”) are underrepresented compared to others. **ROC-AUC** and **PR-AUC** are the standard metrics for this task due to their ability to evaluate model performance under these conditions. Here’s why:

**ROC-AUC (Receiver Operating Characteristic - Area Under Curve)**
•	**Definition**: Measures a model’s ability to distinguish between classes across all thresholds. It plots the true positive rate (TPR, sensitivity) against the false positive rate (FPR, 1-specificity).
•	**Interpretation**:
	•	ROC-AUC = 0.5: No better than random guessing.
	•	ROC-AUC = 1.0: Perfect separation of classes.
•	**Strengths**:
	•	Robust to class imbalance, as it evaluates overall ranking capability (e.g., correctly ranking a “happy” clip higher than a “sad” one).
	•	Widely used for benchmarking general classification tasks.

**PR-AUC (Precision-Recall - Area Under Curve)**
•	**Definition**: Evaluates the precision-recall trade-off, plotting precision (true positives / predicted positives) against recall (true positives / actual positives).
•	**Interpretation**:
	•	PR-AUC close to 1.0: High precision and recall across thresholds.
	•	PR-AUC near 0: Poor performance, especially on minority classes.
•	**Strengths**:
	•	Focuses solely on the positive class (e.g., rare moods like “melancholic”), ignoring true negatives.
	•	More informative than ROC-AUC for imbalanced datasets, as it penalizes false positives (misclassified moods) and false negatives (undetected moods).

## Why These Metrics Are Used for MTG-Jamendo
1. **Class Imbalance Handling:**
	•	MTG-Jamendo’s mood tags are highly skewed (e.g., “energetic” appears frequently, while “dreamy” is rare). PR-AUC prioritizes performance on minority classes, making it ideal for this task [[ref](https://machinelearningmastery.com/roc-curves-and-precision-recall-curves-for-imbalanced-classification/)], [[ref](https://diogoribeiro7.github.io/data%20science/evaluating_binary_classifiers_imbalanced_datasets/)].
	•	ROC-AUC can appear optimistic in imbalanced scenarios but remains useful for overall discriminative power.
2. **Task-Specific Relevance:**
	•	Mood classification requires minimizing false positives (e.g., tagging a calm song as aggressive) and false negatives (missing subtle moods). PR-AUC directly measures this precision-recall balance.
	•	In benchmarks (e.g., MediaEval), PR-AUC is the primary metric due to its sensitivity to tag rarity, while ROC-AUC provides supplementary insights into ranking ability.


## How Are PR-AUC and F1 Score Related?

Both **PR-AUC** (Precision-Recall Area Under the Curve) and **F1 score** are metrics that evaluate a classification model’s ability to balance precision and recall, but they do so in different ways:

- **F1 Score**:
    
    - The F1 score is the _harmonic mean_ of precision and recall, calculated at a single decision threshold.
        
    - It gives a single value summarizing the trade-off between precision and recall for a specific point (usually the default threshold of 0.5).
        
    - Formula: F1=2×Precision×RecallPrecision+RecallF1=2×Precision+RecallPrecision×Recall
        
- **PR-AUC**:
    
    - PR-AUC summarizes model performance _across all possible thresholds_ by measuring the area under the entire precision-recall curve.
        
    - It captures how precision and recall trade off as you vary the threshold for classifying positives.
        
    - A higher PR-AUC means the model maintains a good balance of precision and recall over a range of thresholds.