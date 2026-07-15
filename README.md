# Fraud Detection and Transaction Clustering Project

## Project Overview

This repository presents a machine learning project for financial transaction analysis, focusing on fraud detection and anomaly identification through a structured two-stage workflow.

The first stage uses unsupervised learning to cluster transactions and discover natural groupings in the data. The second stage converts those cluster assignments into labels for a supervised classification model.

The project includes Jupyter notebooks for both clustering and classification, dataset artifacts, and saved model files.

## Step-by-Step Process

1. Explore the data
   - Review the transaction dataset and understand the features.
   - Key transaction attributes include TransactionID, AccountID, TransactionAmount, TransactionType, Location, DeviceID, IP Address, MerchantID, AccountBalance, PreviousTransactionDate, Channel, CustomerAge, CustomerOccupation, TransactionDuration, and LoginAttempts.
   - Confirm data readiness for modeling and identify any preprocessing requirements.

2. Preprocess the dataset
   - Encode categorical values using label encoding or other appropriate transformations.
   - Scale numerical features so clustering and classification algorithms can learn effectively.
   - Prepare the feature matrix for both clustering and supervised training.

3. Build clustering models
   - Apply KMeans clustering to segment transactions into groups.
   - Use PCA to reduce dimensionality for visualization and to help interpret cluster structure.
   - Evaluate clustering quality using silhouette score and other cluster validity metrics.
   - Save the clustering model and attach cluster labels to the dataset for the classification stage.

4. Train classification models
   - Load the labeled dataset from the clustering stage (`data_clustering.csv` or `data_clustering_inverse.csv`).
   - Split the data into training and testing sets.
   - Train supervised classifiers such as Decision Tree and Random Forest.
   - Perform hyperparameter tuning with GridSearchCV or RandomizedSearchCV to improve model performance.
   - Evaluate the final model with metrics like accuracy, precision, recall, and F1-score.
   - Persist the best classification model for future inference.

5. Save and reuse artifacts
   - Store the cleaned dataset, cluster labels, and trained model artifacts for reproducibility.
   - Reuse saved models for inference or further analysis without retraining from scratch.

## Repository Contents

- `[Clustering]_Submission_Akhir_BMLP_Ridho_Rezky_Anwar.ipynb` - Clustering notebook for unsupervised transaction segmentation.
- `[Klasifikasi]_Submission_Akhir_BMLP_Ridho_Rezky_Anwar.ipynb` - Classification notebook that uses cluster labels to train supervised models.
- `data_clustering.csv` - Cluster-labeled dataset for classification.
- `data_clustering_inverse.csv` - Alternative labeled dataset based on cluster interpretation.
- `decision_tree_model.h5` - Saved Decision Tree classification model.
- `model_clustering.h5` - Saved clustering model.
- `PCA_model_clustering.h5` - Saved PCA dimensionality reduction model.
- `tuning_classification.h5` - Saved tuned classification model.

## How to Use

1. Open the clustering notebook in Jupyter or Google Colab.
2. Execute all cells in the clustering notebook to generate cluster labels and save the labeled dataset.
3. Open the classification notebook.
4. Execute all cells in the classification notebook to train, evaluate, and save the final model.

## Goals

- Discover transaction patterns using unsupervised clustering.
- Convert cluster structure into training labels for supervised learning.
- Build a classifier capable of identifying transaction groups and potential anomalies.
- Save workflow artifacts to support reproducibility and portfolio presentation.
