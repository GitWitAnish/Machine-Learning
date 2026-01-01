# Diabetes Prediction

A small notebook-based project that trains a binary classifier to flag likely diabetes cases from tabular features.

## Contents

- Notebook: [Diabetes Prediction/main.ipynb](Diabetes%20Prediction/main.ipynb)
- Data: [Diabetes Prediction/train.csv](Diabetes%20Prediction/train.csv) and [Diabetes Prediction/test.csv](Diabetes%20Prediction/test.csv)
- Output: [Diabetes Prediction/submission.csv](Diabetes%20Prediction/submission.csv) (written after running the notebook)

## Pipeline (in the notebook)

1. Load train/test CSVs with pandas.
2. Inspect schema and missingness via `info`, `describe`, and `isna().sum()`.
3. Label-encode categorical columns with `sklearn.preprocessing.LabelEncoder`.
4. Split features/target (`diagnosed_diabetes`) with an 80/20 train/validation split.
5. Train an `xgboost.XGBClassifier` (200 trees, depth 5, learning rate 0.05, subsample and colsample 0.9).
6. Evaluate accuracy on the held-out validation set.
7. Fit on full training data and generate predictions for the test set.
8. Export a Kaggle-style CSV (`submission.csv`) with `id` and `diagnosed_diabetes`.

## How to run

- Python >=3.9 with `pandas`, `numpy`, `scikit-learn`, `xgboost`, `matplotlib`, `seaborn` installed (e.g., `pip install pandas numpy scikit-learn xgboost matplotlib seaborn`).
- Open the notebook in VS Code or Jupyter and run top to bottom. The last cell writes `submission.csv` beside the notebook.

## Notes

- The dataset files are large; use a local machine instead of a remote synced environment to avoid sync size limits.
- The current setup uses simple label encoding; consider one-hot encoding and hyperparameter tuning if you need better performance.
