# Decision Tree Breast Cancer Classification

## Overview

Decision Tree Breast Cancer Classification is a beginner-friendly machine learning project focused on using a decision tree model to classify breast cancer tumors as benign or malignant.

The goal of this project is not just to train a model, but to understand the full process behind a basic classification workflow. The notebook walks through loading the data, preparing it for modeling, training decision tree classifiers, comparing model settings, and evaluating how well the model performs.

This project is a practical introduction to supervised machine learning using Python and scikit-learn.

## Why This Project Exists

This project was created to practice one of the most important beginner concepts in machine learning: classification.

A decision tree is a useful first model because it is easier to understand than many other algorithms. Instead of acting like a black box, a decision tree makes predictions by splitting data based on feature values. This makes it a strong starting point for learning how models make decisions.

Through this project, I practiced:

- Loading and preparing a classification dataset
- Splitting data into training and testing sets
- Training a Decision Tree Classifier
- Comparing Gini impurity and entropy criteria
- Tuning tree depth to manage overfitting
- Evaluating model performance with accuracy, precision, recall, and F1-score
- Interpreting the tradeoffs between false positives and false negatives

## Project Workflow

The notebook follows a structured machine learning workflow.

### 1. Setup and Data Loading

The project begins by importing the required Python libraries and loading the breast cancer dataset. This step establishes the features used by the model and the target variable the model is trying to predict.

### 2. Data Preparation

The data is separated into input features and target labels. The dataset is then split into training and testing sets so the model can be evaluated on data it has not already seen.

### 3. Model Training

A decision tree classifier is trained to predict whether a tumor is benign or malignant. The project explores how different tree settings affect the model's behavior and performance.

### 4. Model Evaluation

The trained model is evaluated using classification metrics. These metrics help explain not only how often the model is correct, but also how well it performs for each class.

This is especially important in a medical dataset, where missing a malignant tumor can be more serious than incorrectly flagging a benign one.

### 5. Model Comparison and Tuning

The notebook compares different decision tree configurations, including Gini impurity and entropy. It also tests different tree depths to better understand the balance between a model that is too simple and one that overfits the training data.

## Tools Used

This project uses common Python machine learning tools:

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

## Getting Started

Clone the repository:

    git clone https://github.com/frankstop/DecisionTree_BreastCancer.git
    cd DecisionTree_BreastCancer

Install the main dependencies:

    pip install pandas numpy matplotlib seaborn scikit-learn jupyter

Open the notebook:

    jupyter notebook

Then open the project notebook.

You can also open the exported HTML file in a browser to view the notebook without running the code.

## Who This Project Is For

This project is best suited for:

- Beginners learning machine learning
- Students practicing classification models
- Anyone learning how decision trees work
- Portfolio reviewers who want to see a structured modeling workflow
- Learners who want practice interpreting model evaluation metrics

## What I Practiced

Through this project, I practiced building a supervised machine learning model from start to finish. I worked with a real classification dataset, trained decision tree models, compared different splitting criteria, and evaluated performance using metrics that go beyond simple accuracy.

The project helped reinforce how model settings affect results and why evaluation should consider both overall performance and class-specific behavior.

## Future Improvements

Possible next steps for this project include:

- Adding a requirements.txt file
- Adding more markdown explanations throughout the notebook
- Using cross-validation for more reliable model evaluation
- Visualizing feature importance
- Adding ROC AUC analysis
- Testing pruning or cost-complexity regularization
- Comparing the decision tree against Random Forest or Gradient Boosting models
- Creating a short final summary of key findings

## Author

Created by [frankstop](https://github.com/frankstop)
