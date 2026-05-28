# cardiac-ml-model
Binary classification model predicting heart disease in 297 cardiac patients using Random Forest, SHAP interpretability analysis, and GridSearchCV hyperparameter tuning. Built in Python with scikit-learn. Achieves 88% accuracy and AUC of 0.94.
# Heart Disease Binary Classifier

A machine learning project predicting the presence of heart disease in cardiac patients using the UCI Heart Disease dataset.

## Project Overview

This project builds, evaluates, and optimizes a Random Forest binary classification model to predict heart disease diagnosis (positive/negative) from 13 clinical features including age, cholesterol, chest pain type, maximum heart rate, and number of major vessels. The model was built in Python using scikit-learn and includes SHAP-based interpretability analysis and hyperparameter tuning via GridSearchCV.

## Dataset

UCI Machine Learning Repository — Heart Disease Dataset (Cleveland)
- 303 patients, 13 clinical features
- Target variable converted from 5-class severity to binary (0 = no disease, 1 = disease present)
- 6 rows with missing values dropped, leaving 297 patients
- Source: https://archive.ics.uci.edu/dataset/45/heart+disease

## Methods

- Data preprocessing: StandardScaler feature normalization, compute_class_weight for class balancing, 80/20 train/test split
- Model: Random Forest Classifier (scikit-learn)
- Interpretability: SHAP TreeExplainer with summary plot visualization
- Optimization: GridSearchCV hyperparameter tuning across 27 parameter combinations with 5-fold cross validation

## Results

| Metric | Original Model | Tuned Model |
|--------|---------------|-------------|
| Accuracy | 88.3% | 85.0% |
| AUC Score | 0.9398 | 0.9468 |

Confusion matrix (tuned model): 32 true negatives, 21 true positives, 3 false positives, 4 false negatives.

## Key Findings

SHAP analysis revealed the most influential predictors of heart disease in this dataset:
1. ca (number of major vessels colored by fluoroscopy)
2. thal (thalassemia type)
3. cp (chest pain type)
4. thalach (maximum heart rate achieved) — inversely related to disease prediction

These findings are consistent with established cardiology literature, suggesting the model learned clinically meaningful patterns rather than noise.

## Tools and Libraries

- Python 3
- scikit-learn
- SHAP
- pandas
- numpy
- matplotlib
- Google Colab

## How to Run

1. Open the .ipynb file in Google Colab or Jupyter Notebook
2. Run all cells in order
3. All required libraries are installed in Cell 1

## Author

Audry J. Carruth
audry.j.c@gmail.com
linkedin.com/in/audrycarruth
