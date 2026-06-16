# Multi-Label Heart Disease Classification using ECG Signals

## Overview

This project presents an end-to-end machine learning and deep learning framework for automated multi-label heart disease classification using 12-lead Electrocardiogram (ECG) signals from the PTB-XL dataset.

The system combines ECG signal preprocessing, PQRST segmentation, handcrafted feature extraction, and deep learning architectures to classify multiple cardiac conditions simultaneously.

## Dataset

**PTB-XL: A Large Publicly Available Electrocardiography Dataset**

- 21,799 clinical 12-lead ECG recordings
- 18,869 patients
- 100 Hz and 500 Hz sampling frequencies
- Multi-label diagnostic annotations

Dataset Link:
https://physionet.org/content/ptb-xl/

## Target Classes

The model predicts the following cardiac conditions:

- NORM (Normal ECG)
- IMI (Inferior Myocardial Infarction)
- ASMI (Anterior Septal Myocardial Infarction)
- LVH (Left Ventricular Hypertrophy)
- NDT (Non-Diagnostic ECG)
- LAFB (Left Anterior Fascicular Block)

## Project Pipeline

1. ECG Data Acquisition
2. Signal Preprocessing
   - Noise Filtering
   - Baseline Wander Removal
   - Normalization
3. PQRST Detection using Christov Algorithm
4. Feature Extraction
5. Machine Learning & Deep Learning Model Training
6. Multi-Label Classification
7. Performance Evaluation

## Feature Engineering

Extracted 132 clinically meaningful ECG features including:

- PR Ratio
- RR Distance
- P Energy
- QRS Energy
- T Energy
- Normalized QT Interval
- PQ Distance
- ST Slope
- PR Slope
- R-S-Q Difference
- Heart Rate

## Models Implemented

### Traditional Machine Learning

- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- XGBoost

### Deep Learning

- 1D CNN
- LSTM
- CNN + BiLSTM
- ResNet18
- DenseNet121
- EfficientNet-B0
- STFT + 2D CNN

### Fusion Architecture

M4 Fusion Model combining:

- M1: 1D CNN on raw ECG signals
- M2: STFT-based 2D CNN
- M3: Handcrafted ECG Features
- M4: Fusion Network

## Results

### Baseline Machine Learning Models

| Model | Accuracy | F1 Score |
|---------|----------|-----------|
| Logistic Regression | 0.865 | 0.624 |
| Random Forest | 0.893 | 0.660 |
| SVM | 0.820 | 0.580 |
| KNN | 0.876 | 0.461 |

### Deep Learning Models

| Model | Accuracy |
|---------|----------|
| 1D CNN | 0.924 |
| CNN + BiLSTM | 0.918 |
| LSTM | 0.911 |

### Fusion Model Performance

| Model | Accuracy | Precision | Recall | F1 Score | AUROC |
|---------|----------|-----------|--------|----------|--------|
| M4 Fusion | 0.9202 | 0.7834 | 0.6295 | 0.6854 | 0.9510 |

## Technologies Used

- Python
- NumPy
- Pandas
- Scikit-Learn
- TensorFlow
- Keras
- PyTorch
- WFDB
- NeuroKit2
- Matplotlib
- Seaborn

## Repository Structure

```text
Multi-Label-Heart-Disease-Classification/
│
├── data/
├── notebooks/
├── src/
├── models/
├── results/
├── figures/
├── requirements.txt
├── README.md
└── LICENSE
```

## Future Work

- Transformer-based ECG Models
- Explainable AI (XAI)
- Real-Time ECG Monitoring
- Clinical Decision Support Integration
- Cross-Dataset Generalization

## Author

**Ashritha Kotagiri**
Master of Science in Data Science
University of North Florida

## Citation

If you use this work, please cite:

Ashritha Kotagiri and Xudong Liu,
"Multi-Label Heart Disease Classification Using Electrocardiograms and Machine Learning",
University of North Florida, 2026.
