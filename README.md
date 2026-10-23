# Subject-Independent Sleep Stage Classification with CNN-BiLSTM

## Overview

This project explores automatic sleep stage classification using a multi-channel deep learning approach combining Convolutional Neural Networks (CNNs) and Bidirectional Long Short-Term Memory networks (BiLSTMs).

The experiments use the Sleep-EDF Expanded Sleep Cassette dataset and focus on subject-independent evaluation, spectral feature extraction, temporal modeling, and the impact of Wake-class imbalance.

## Dataset

- **Dataset:** Sleep-EDF Expanded — Sleep Cassette (SC)
- **Subjects:** 78
- **Recordings:** 153
- **Input channels:** EEG Fpz-Cz, EEG Pz-Oz, and horizontal EOG
- **Epoch duration:** 30 seconds
- **Target classes:** Wake, N1, N2, N3, and REM

The dataset is not included in this repository. Please obtain it from the official [PhysioNet Sleep-EDF Expanded dataset](https://physionet.org/content/sleep-edfx/).

## Methodology

1. Signal preprocessing and bandpass filtering
2. Log-STFT spectrogram feature extraction
3. Temporal Wake-cropping strategy
4. Subject-independent train, validation, and test splits
5. CNN-based spectral feature extraction
6. BiLSTM temporal modeling over five consecutive epochs
7. Baseline comparisons and model-pruning experiments

## Test Results

### Wake-cropped CNN-BiLSTM

| Metric | Score |
|---|---:|
| Accuracy | 78.06% |
| Macro F1-score | 75.84% |
| Cohen's Kappa | 0.7084 |

### Uncropped CNN-BiLSTM

| Metric | Score |
|---|---:|
| Accuracy | 91.38% |
| Cohen's Kappa | 0.8275 |

The uncropped test set contains a substantially higher proportion of Wake epochs. Therefore, accuracy should not be interpreted in isolation when comparing the two settings. Macro F1-score and per-class metrics are also important for understanding performance across sleep stages.

## Repository Contents

- `sleep_stage_class.ipynb` — preprocessing, model training, evaluation, and experiments.


## Authors

**Dikra Habsaoui** and **Imane Chaabani**
