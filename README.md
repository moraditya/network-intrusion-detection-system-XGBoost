# Network Intrusion Detection System with XGBoost

This project demonstrates a binary and multiclass classification model using XGBoost to detect different types of network attacks. The dataset used includes a variety of attack types, and the project implements techniques to handle class imbalance using SMOTE, and then uses XGBoost for binary classification to detect if the model 1. an attack or 2. presents normal behavior and for multiclassification to determine the type of attack any given row might be.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
  - [Data Sources](#data-sources)
  - [Data Preprocessing](#data-preprocessing)
- [Binary Classification](#binary-classification)
- [Multiclass Classification](#multiclass-classification)
- [Model Evaluation](#model-evaluation)
  - [Cross-Validation](#cross-validation)
  - [Performance Metrics](#performance-metrics)
- [GUI for Testing Predictions](#gui-for-testing-predictions)
- [Technologies Used](#technologies-used)
- [How to Run](#how-to-run)
  - [Installing Dependencies](#installing-dependencies)
  - [Running the GUI](#running-the-gui)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
The goal of this project is to create a machine learning model that classifies network traffic as either normal or one of several types of attacks. Both binary and multiclass classification models are built using the **XGBoost** classifier. The models handle the class imbalance problem using **SMOTE** (Synthetic Minority Over-sampling Technique).

In addition, a simple **Tkinter GUI** is built to allow users to input a test index and predict the attack type for that specific row.

## Dataset

### Data Sources
The dataset contains multiple types of network attacks and normal traffic. The CSV files are combined into a single dataset for training and testing. Below are the attack types included:
- Back
- Buffer Overflow
- FTP Write
- Guess Password
- Neptune
- NMap
- Normal
- Port Sweep
- Rootkit
- Satan
- Smurf

### Data Preprocessing
1. Data from multiple CSV files is loaded and concatenated into a single DataFrame.
2. An `attack_binary` column is created to represent attack types as `1` and normal traffic as `0`.
3. Label encoding is applied for multiclass classification to convert attack types into numeric labels.
4. Missing values are handled, and SMOTE is applied to deal with class imbalance in both binary and multiclass scenarios.

## Binary Classification
In the binary classification task, network traffic is classified as either "normal" or "attack." The XGBoost classifier is trained on the dataset after applying SMOTE to address class imbalance. The key steps include:
- Train-test split (80/20)
- Application of SMOTE for class balancing
- XGBoost model training
- Cross-validation for overfitting check

## Multiclass Classification
In the multiclass classification task, network traffic is classified into one of the following categories:
- Normal
- Back
- Buffer Overflow
- FTP Write
- Guess Password
- Neptune
- NMap
- Port Sweep
- Rootkit
- Satan
- Smurf

Similar to binary classification, SMOTE is used to balance the dataset before training the XGBoost model.

## Model Evaluation

### Cross-Validation
The model performance is evaluated using **5-fold cross-validation** to ensure the model generalizes well across unseen data. Cross-validation is performed for both binary and multiclass classification tasks.

### Performance Metrics
For binary classification, the following metrics are reported:
- Accuracy
- Precision
- Recall
- F1-Score

For multiclass classification, the accuracy and detailed classification reports (precision, recall, F1-score for each class) are included.

## GUI for Testing Predictions
A simple **Tkinter GUI** allows users to test the model's predictions. Users can input a row index from the test set, and the GUI displays the predicted attack type and the actual attack type for that row. It also indicates whether the prediction was correct.

![image](https://github.com/user-attachments/assets/65ecd501-4a94-46af-8b0a-27940aa29cd2)

## Technologies Used
- **Python**: Core language used for building the project.
- **XGBoost**: Classifier used for both binary and multiclass classification.
- **SMOTE**: Synthetic Minority Over-sampling Technique used to handle class imbalance.
- **Tkinter**: Python's standard GUI toolkit used to create the simple user interface.
- **Pandas**: For data manipulation and loading CSV files.
- **Scikit-learn**: For train-test split, label encoding, and evaluation metrics.

## How to Run

### Installing Dependencies
First, clone the repository and navigate to the project directory. Install the required Python libraries by running:

```bash
pip install -r requirements.txt
