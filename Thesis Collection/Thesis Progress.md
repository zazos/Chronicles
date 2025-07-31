- Decently satisfied with multi label (clustered) version of the model. 
- The valence-arousal values are not good though (check va_plane_predictions.png from musav project)
	- if these values get fixed, proceed to webapi
- Decided to swap to Wav2Vec pre-trained model, freezing it except a regression head for my data set. 

---
### Wav2Vec

- Fully frozen backbone to treat it as **baseline**.
- Results are not exceptional, but i won't be fine-tuning anything more.
	- Approximately 10 minutes per epoch to train.
- An analysis on the va plane:
	- **Regression to the Mean:** The most noticeable characteristic is that the model's predictions (orange dots) are clustered much more tightly in the center than the ground truth data (blue dots). This is a classic case of "regression to the mean," where the model learns the average distribution of the training data but struggles to predict the more extreme high or low values. It's hesitant to make bold predictions.
	- **Poor Valence Prediction:** The predictions are concentrated in a very narrow vertical band, indicating that the model predicts a similar valence value (around 0.5) for most songs, regardless of their true valence. This suggests the model has learned very little about predicting the valence dimension.
	- **Better Arousal Prediction:** The predictions show a wider spread along the arousal (vertical) axis compared to the valence axis. This indicates the model has had more success in learning to distinguish between low and high arousal levels.

- Fastest and Simplest: It's the quickest way to get a result because you are training the fewest possible parameters.
- Pure Feature Extraction: You are testing the raw, off-the-shelf feature extraction capabilities of the pre-trained Wav2Vec2 model for your specific task.

---

### Why Transfer Learning is the Right Choice Here (using resnet's embeddings for valence-arousal)

- **Shared Feature Representation:** The core of both tasks is to learn a meaningful representation of a Mel-spectrogram. The features that distinguish a "happy" song (high valence, high arousal) from a "sad" song (low valence, low arousal) are the exact same kinds of features needed for valence-arousal regression. Your mood classification model has already learned to identify the acoustic patterns related to emotional content.

- **Moods are Points in the VA Space:** The 11 mood labels are essentially discrete points or regions within the continuous Valence-Arousal (VA) space. By learning to separate these moods, your model has implicitly learned the underlying VA dimensions.

- Scrap Wav2Vec altogether.
	- Training time was about 10 minutes per epoch.
	- Model size was 360MB (very large).
	- Performance was poor, to actual knowledge gained. 

---

### Training issues

- Precision-recall trade-offs
- Over-predicting labels

---

### Swapped to Single Label 

- multi labeling results were undistinguishable when reviewing the results on the test set
- stark contrast precision vs recall, even after heavy parameterisation (degenerate learning)
- For the purposes of presenting a webapi that is functionable, i needed a model that at least know how to pick a single label out of a track
- From 56 labels to 11–a different way of PCA with llm clustered names
	- 7567 dataset size (from 17984)
	- Originally the single label dataset included 2023 additional datapoints that were labeled from the LLM as Noise Point–their labels did not have any neighbouring cluster.