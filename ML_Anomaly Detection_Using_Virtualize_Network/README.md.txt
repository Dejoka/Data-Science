# Integration of Machine Learning Techniques for Anomaly Detection in Virtualized Networks

## Project Overview

This research project evaluates the effectiveness of five machine learning algorithms for automated network intrusion detection in virtualized environments. Using the CICIDS2017 benchmark dataset, the study demonstrates that ensemble methods, particularly Random Forest, achieve exceptional detection accuracy while maintaining computational efficiency.

## Problem Statement

Traditional signature-based intrusion detection systems struggle with:
- Zero-day exploits and novel attack patterns
- High false positive rates in dynamic virtualized environments
- Inability to adapt to evolving network traffic patterns
- Limited effectiveness against advanced persistent threats

This project addresses these limitations through machine learning-based anomaly detection.

## Dataset

*CICIDS2017 - Canadian Institute for Cybersecurity Intrusion Detection System 2017
- Total Records: 164,573 network traffic flows
- Features: 80 original features reduced to 40 through feature selection
- Classes: Binary classification (Benign/Attack)
- Attack Types: DoS, DDoS, Brute Force, Web Attacks, Botnet, Infiltration, Port Scanning

## Methodology

### Data Preprocessing
1. Data Cleaning: Removed missing values, duplicates, and infinite values
2. Feature Engineering: Multi-criteria selection (correlation analysis, chi-square testing, variance thresholding)
3. Class Balancing: Applied SMOTE to training set (50-50 balance)
4. Normalization: Z-score standardization
5. Data Split: 79.3% training, 10.4% validation, 10.4% test

### Machine Learning Algorithms Evaluated

1. Random Forest - Ensemble of decision trees
2. Gradient Boosting - Sequential ensemble method
3. Decision Tree - Single tree classifier
4. K-Nearest Neighbors (KNN) - Distance-based classifier
5. Artificial Neural Network (ANN-MLP) - Multi-layer perceptron

## Results

### Performance Comparison (Test Set)

| Model | Accuracy | Precision | Recall | F1-Score | AUC | Rank |
|-------|----------|-----------|--------|----------|-----|------|
| *Random Forest* | *99.80%* | *99.32%* | *99.58%* | *99.45%* | *99.99%* | *1st* |
| Gradient Boosting | 99.70% | 98.91% | 99.45% | 99.18% | 99.99% | 2nd |
| Decision Tree | 99.66% | 98.50% | 99.65% | 99.07% | 99.82% | 3rd |
| KNN | 99.42% | 97.71% | 99.13% | 98.41% | 99.66% | 4th |
| ANN-MLP | 97.88% | 90.36% | 98.87% | 94.42% | 99.88% | 5th |

### Key Findings

 Random Forest achieved best overall performance* with 99.80% accuracy and near-perfect discrimination (99.99% AUC)

 Extremely low error rates:
- False Positive Rate: 0.15% (only 21 out of 13,975 benign instances misclassified)
- False Negative Rate: 0.42% (only 13 out of 3,099 attacks missed)

Tree-based algorithms dominated: Top 3 models all used decision tree architectures

Consistent generalization: Validation and test performance remained stable across all models

### Computational Efficiency

| Model | Training Time | Inference Time | Model Size |
|-------|---------------|----------------|------------|
| KNN | 0.05s | 0.723ms | 40.80 MB |
| Decision Tree | 3.28s | *0.0003ms* | *0.048 MB* |
| Random Forest | 32.39s | 0.016ms | 14.29 MB |
| ANN-MLP | 44.54s | 0.001ms | 0.22 MB |
| Gradient Boosting | 174.71s | 0.003ms | 0.57 MB |

Decision Tree offers fastest inference and smallest footprint, while *Random Forest* provides optimal balance between accuracy and efficiency.

## Technologies Used

- Programming Language: Python
- Statistical Analysis: SMOTE, feature selection techniques