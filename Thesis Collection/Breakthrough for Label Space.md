# Pipeline for Creating Acoustically Coherent Track Labels

## Overview

The goal is to bridge the gap between semantic (text-based) and acoustic (audio-based) labels by creating new, acoustically consistent categories for your music tracks. This approach leverages low-level acoustic features to group tracks, resulting in more meaningful and robust labels for downstream tasks like deep neural network (DNN) training.
## Step 1: Cluster Tracks Based on Acoustic Features

- **Data**: Use the low-level acoustic features (e.g., BPM, spectral centroid) available for all 18,000 tracks.
- **Preprocessing**:
    - Scale all features using `sklearn.preprocessing.StandardScaler` so each has mean 0 and standard deviation 1.
    - This normalization is crucial because features can have very different ranges.
- **Clustering Algorithm**:
    - Start with K-Means clustering.
    - Choose the number of clusters (K) based on your target label count (e.g., K=5 to 10).
    - Optionally, use the Elbow Method or Silhouette Score to determine the optimal K in a data-driven way.
- **Output**: A mapping from each track ID to its assigned acoustic cluster.
    

## Step 2: Profile and Label the Acoustic Clusters

- **Profiling**:
    - For each acoustic cluster, gather all tracks assigned to it.
    - Examine the original 56 ground-truth labels for these tracks.
    - Count the frequency of each original label within the cluster.
- **Example**:
    - Cluster 0 might contain 2,000 tracks.
    - Its top 5 original labels: fast (1,500), dance (1,300), party (1,200), upbeat (1,100), fun (900).
    - Cluster 1 might have slow, calm, relaxing, ambient, meditative as top labels.
- **Labeling**:
    - Assign a new, broad, and meaningful name to each cluster based on its dominant original labels.
        - E.g., Cluster 0 → "High-Energy / Dance"
        - E.g., Cluster 1 → "Calm / Ambient"
    - Optionally discard clusters that are too small or lack a clear theme.

## Step 3: Train DNN on the New, Coherent Labels

- **Create the New Corpus**:
    - Generate a new CSV file with two columns: `track_id` and `new_acoustic_label`.
    - `tracks_with_cluster_names.csv`
- **Train**:
    - Use existing training script (`clustered_single_label_train.py`).
    - Point it to the new corpus.
    - Instead of fine tuning the backbone or a part of it's layers, completely freeze the backbone and inject lora adapters. 
	    - It's like giving a small set of 'sticky notes'/'tiny adapter' for each layer. When a spectrogram enters, the model uses it's pre-existing knowledge, but also glancing at the sticky notes for task-specific adjustments.
	    - `lora_A` and `lora_B` very small adapters injected in parallel with an existing frozen layer 
	    - The key idea is **Low Rank Decomposition**: A large matrix (like the weight matrix of a NN layer) can often be approximated by multiplying two much smaller, "skinnier" matrices. The `rank` is the size of that small inner dimension. 
	    - (NOTE) when reporting, add mathematical equations.
- **Expected Benefit**:
    - The DNN now learns from acoustically distinct classes, improving its ability to model underlying patterns and boosting performance.


## Step 4: Transfer learning to MusAV

- Extract 512 embeddings of the model produced from Step 3
- Train a simple MLP with 30 sec Spotify tracks annotated with valence-arousal values but with the embeddings of my model instead as training points.
- Result: av_regressor.pth


## Step 5: Inference Lookup Table

- `clustered_training/unified_inference.py`: Takes the test-split and inference both resnet and av_regressor model
- Save the results to `data/inference_lookup.csv` for recommendation system on the webapi


## Step 6: WebAPI

- Carefully transfer the datasets and the two models
	- Mainly the test-split and the inference lookup
	- Maybe the label_to_idx as well for label encoding alignment?
- Re-implement the visualizations to to align with the new label space and datasets.
## Additional Notes

- **Clustering vs. t-SNE**:
    - The approach is similar in spirit to t-SNE, which visually arranges similar data points together.
    - By clustering acoustic features and then analyzing label distributions, we achieve a scalable, programmatic version of what t-SNE does visually.
- **Result**:
    - The pipeline directly addresses the semantic-acoustic disconnect and creates a high-quality, acoustically consistent dataset for your web API and machine learning models.

## Summary Table

|Step|Purpose|Key Actions|Output|
|---|---|---|---|
|1. Cluster|Group tracks by acoustic similarity|Scale features, apply K-Means|track_id → cluster_id|
|2. Profile & Label|Understand and name clusters|Analyze label distribution in each cluster|cluster_id → new_acoustic_label|
|3. Train|Build better models|Create new corpus, train DNN|Improved classification|

---

