ECG Beat Classification: Traditional ML vs. Deep Learning (CNN)
This project explores the classification of Electrocardiogram (ECG) heartbeats using the MIT-BIH Noise Stress Test Database. It implements two different approaches for arrhythmia detection: a traditional Machine Learning approach (Random Forest) and a Deep Learning approach (Convolutional Neural Networks - CNN).

Overview
The goal is to accurately classify different types of heartbeats from raw ECG signals. The project covers the entire pipeline from data loading and preprocessing to feature extraction and model evaluation.

 Dataset
Database: MIT-BIH Noise Stress Test Database (118e00 record).

Library used: wfdb for reading physiological signals and annotations.

Beat Types: Includes various annotations such as Normal (N), Premature Ventricular Contractions (V), and others.

🚀Key Features
1. Data Preprocessing & Visualization
Loading ECG records and annotations using wfdb.

Mapping annotations to specific signal samples.

Visualizing raw ECG signals and marking beat locations.

Segmenting continuous signals into individual heartbeats using a fixed window size.

2. Traditional Machine Learning Approach
Feature Extraction: Manual extraction of statistical features (Mean, Standard Deviation, Max, Min) from each beat segment.

Model: Random Forest Classifier.

Evaluation: Includes Classification Report and Confusion Matrix visualization using seaborn.

3. Deep Learning Approach (CNN)
Data Preparation: Reshaping raw signal segments for 1D-Convolutional layers.

Architecture: - Multiple Conv1D layers for automatic feature extraction.

MaxPooling1D for dimensionality reduction.

Dense layers with Dropout for classification and preventing overfitting.

Optimization: Uses Adam optimizer and Sparse Categorical Crossentropy loss.

Visualization: Training vs. Validation accuracy plots.

 Requirements
To run this code, you need the following Python libraries:

Bash
pip install numpy pandas matplotlib seaborn wfdb scikit-learn tensorflow
 Results
The Random Forest provides a quick baseline using statistical features.

The CNN model achieves high accuracy by learning spatial patterns directly from the raw ECG waveforms without manual feature engineering.

Project Structure
Data Loading: Importing .dat and .atr files.

Segmentation: Slicing the signal into 200-300 sample windows around each R-peak.

Classification: Training and testing the models.

Analytics: Plotting confusion matrices and learning curves.
 How to use
Clone the repository.

Update the path variable in the script to point to your local MIT-BIH dataset directory.

Run the cells in a Jupyter Notebook or an IDE like PyCharm/VSCode.
