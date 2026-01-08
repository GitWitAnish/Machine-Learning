# Health Risk Classifier

A machine learning project that predicts health risk classes based on environmental, socioeconomic, and geographic factors.

## Overview

This project uses environmental data, weather patterns, and socioeconomic indicators to classify health risk levels. The model leverages XGBoost for multi-class classification to predict health risk categories.

## Dataset

The project uses two datasets:

- `train.csv` - Training data with labeled health risk classes
- `test.csv` - Test data for predictions

### Features

The dataset includes the following features after preprocessing:

**Environmental & Weather Features:**

- `drought_indicator` - Binary indicator for drought conditions
- `extreme_weather_events` - Count of extreme weather events
- `heat_wave_days` - Number of heat wave days
- `flood_indicator` - Binary indicator for flood conditions
- `precipitation_mm` - Precipitation in millimeters
- `temp_anomaly_celsius` - Temperature anomaly in Celsius
- `air_quality_index` - Air quality index value
- `pm25_ugm3` - PM2.5 particulate matter levels

**Geographic Features:**

- `country_code` - ISO country code (one-hot encoded)
- `region` - Geographic region (one-hot encoded)
- `latitude` - Geographic latitude (-90 to 90)
- `longitude` - Geographic longitude (-180 to 180)

**Temporal Features:**

- `year` - Year of observation
- `month` - Month (1-12)
- `week` - Week of year (0-53)

**Socioeconomic Features:**

- `income_level` - Income level category (ordinal encoded: 0=Lower-Middle, 1=Upper-Middle, 2=High)
- `gdp_per_capita_usd` - GDP per capita in USD
- `population_millions` - Population in millions
- `food_security_index` - Food security index score
- `mental_health_index` - Mental health index score
- `healthcare_access_index` - Healthcare access index score

**Target Variable:**

- `health_risk_class` - Multi-class health risk category

## Data Preprocessing

The notebook implements extensive data cleaning including:

1. **Boolean Standardization**: Converting various representations (0/1, true/false, yes/no) to consistent binary values
2. **Numeric Cleaning**: Converting strings to numeric values, handling outliers, and rounding appropriately
3. **Geographic Validation**: Ensuring latitude and longitude values are within valid ranges
4. **Categorical Mapping**: Standardizing country codes, regions, and income levels
5. **Encoding**:
   - One-hot encoding for nominal features (country_code, region)
   - Ordinal encoding for income_level
   - Label encoding for categorical features in XGBoost

## Model

**Algorithm**: XGBoost Classifier

**Hyperparameters:**

- `n_estimators`: 1000
- `learning_rate`: 0.05
- `max_depth`: 8
- `subsample`: 0.8
- `colsample_bytree`: 0.8
- `objective`: multi:softprob
- `eval_metric`: mlogloss

## Requirements

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
```

## Usage

1. **Load and explore data:**

```python
train_df = pd.read_csv("train.csv")
test_df = pd.read_csv("test.csv")
```

2. **Run the notebook cells sequentially** to:

   - Clean and preprocess all features
   - Encode categorical variables
   - Split data into training and validation sets
   - Train the XGBoost model
   - Evaluate performance

3. **Evaluation Metrics:**
   - Accuracy Score
   - Log Loss (mlogloss)

## Project Structure

```
Health Risk Classifier/
├── main.ipynb          # Main analysis notebook
├── train.csv           # Training dataset
├── test.csv            # Test dataset
└── README.md           # Project documentation
```

## Results

The model outputs:

- **Accuracy**: Classification accuracy on validation set
- **Log Loss**: Multi-class log loss for probability predictions

## Future Improvements

- Feature engineering (interaction terms, temporal features)
- Ensemble methods (combining multiple models)
- Missing value imputation strategies
- Feature importance analysis
- Cross-validation for more robust evaluation
