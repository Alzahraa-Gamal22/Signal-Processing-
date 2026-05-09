ECG-Noise-Classifier
Sub-title: Robust Signal Quality Assessment using Deep 1D-Convolutional Neural Networks
1. Project Definition
This project focuses on the automated classification of noise artifacts in Electrocardiogram (ECG) signals. Using the MIT-BIH Noise Stress Test Database, I developed a deep learning model to distinguish between clean cardiac signals and three prevalent types of clinical noise. The goal is to provide a pre-processing layer for medical AI systems to ensure diagnostic reliability by identifying corrupted data segments.

2. Technical Objectives
Signal Pre-processing: Implement DC-offset removal and Z-score normalization to standardize raw ECG data.

Feature Extraction: Utilize 1D-CNNs to automatically learn spatial and temporal features from signal windows (300 samples).

Model Optimization: Address overfitting and instability using Global Average Pooling, Dropout, and Learning Rate Schedulers.

Performance Analysis: Evaluate the model using Confusion Matrices and F1-scores to understand class-specific challenges (e.g., EM noise vs. Clean signals).

3. Dataset & Noise Types
The model is trained to classify four distinct categories:

Clean: Undistorted ECG signals.

BW (Baseline Wander): Low-frequency noise caused by breathing or electrode movement.

EM (Electromyogram): High-frequency noise caused by muscle contractions.

MA (Motion Artifact): Rapid baseline shifts caused by patient movement.

4. Model Architecture
The architecture is designed for high efficiency and low parameter count:

3x Conv1D Layers: With Batch Normalization and ReLU activation for deep feature extraction.

Global Average Pooling: Replaces traditional Flattening to make the model invariant to signal shifts and reduce overfitting.

Dense & Dropout: A 64-unit fully connected layer with 50% dropout for robust regularization.

Softmax Output: 4-way classification.

5. Key Results
Overall Accuracy: 94%

High Performance: Achieved >97% F1-score for BW and MA noise types.

Stability: Successfully stabilized the validation curve, reaching convergence through adaptive learning rates.

Insight: Identified a common signal processing challenge where high-frequency EM noise occasionally overlaps with the sharp QRS complexes of clean signals.

6. Tech Stack
Language: Python

Deep Learning: TensorFlow / Keras

Signal Processing: WFDB, Scipy

Data Science: Scikit-learn, NumPy, Pandas

Visualization: Matplotlib, Seaborn
