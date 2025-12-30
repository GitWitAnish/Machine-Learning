# NASA Asteroid Classification

A machine learning project to predict whether asteroids are potentially hazardous to Earth based on their orbital and physical characteristics.

## Project Overview

This project analyzes NASA's asteroid dataset to build a binary classification model that predicts whether an asteroid is hazardous or not. The model evaluates multiple machine learning algorithms and selects the best performing one.

## Dataset

The dataset (`nasa.csv`) contains information about asteroids including:

- Orbital parameters
- Physical characteristics (estimated diameter)
- Velocity metrics
- Miss distance measurements
- Hazardous classification (target variable)

### Features Used

After preprocessing, the following features are retained:

- Absolute Magnitude
- Est Dia in KM (min & max)
- Relative Velocity km per sec
- Miss Dist.(Astronomical)

Removed features include identifiers, dates, and redundant measurements in different units.

## Models Evaluated

The project compares the following classification algorithms:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

Each model is evaluated using:

- 5-fold cross-validation
- Train/test split (80/20)
- Accuracy metrics

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
```

## How to Run

1. Ensure all required libraries are installed
2. Place the `nasa.csv` dataset in the project directory
3. Open and run `main.ipynb` sequentially
4. The best model will be saved as `best_model.pkl`

## Results

The notebook trains multiple models and automatically selects the best performing one based on test accuracy. The selected model is saved for future predictions.

## Project Structure

```
Nasa Asteroid Classification/
├── main.ipynb          # Main analysis notebook
├── nasa.csv           # Dataset
├── best_model.pkl     # Saved best model (generated)
└── README.md          # This file
```

## Key Insights

- XGBoost feature importance visualization helps identify the most predictive features
- Model comparison ensures the best algorithm is selected for the task
- The hazardous classification is converted to binary (0/1) for model training
