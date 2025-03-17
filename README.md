# Air Quality Prediction using Machine Learning

This repository contains a machine learning project aimed at predicting air quality, specifically the ground truth carbon monoxide (CO(GT)) levels, using data from various sensors. CO(GT) is the most accurate measurement of carbon monoxide, typically obtained using expensive sensors. The goal of this project is to use machine learning to estimate CO(GT) levels using cheaper sensor readings and other pollutant data.

## Project Overview

The project involves the following steps:

1. **Feature Engineering**:
   - **Null Value Removal**: The dataset is cleaned by removing null values.
   - **Outlier Detection**: Outliers are detected using the five-point summary and replaced with appropriate values.
   - **Feature Construction**: New columns are created based on interactions between other gases (e.g., `PT08.S1(CO)_NOx(GT)`, `PT08.S1(CO)_C6H6(GT)`). Additionally, seasonal values (e.g., 'Winter', 'Spring', 'Summer', 'Fall') and time-based features (e.g., 'Morning', 'Afternoon', 'Evening', 'Night') are derived from the date and time columns.

2. **Correlation Analysis**:
   - A correlation analysis is performed to identify linear relationships between CO(GT) and other features.

3. **Model Training and Evaluation**:
   - **Linear Regression**: 
     - Train R² Score: 0.8897930568286733
     - Test R² Score: 0.8928599242397163
   - **Random Forest**:
     - Train R² Score: 0.9717013141006248
     - Test R² Score: 0.9259672837284636
     - OOB Score: 0.9238438699531566
   - **Hyperparameter Tuning**:
     - Best Parameters: `{'max_depth': 30, 'min_samples_leaf': 1, 'min_samples_split': 2, 'n_estimators': 1000}`
   - **Gradient Boosting Regressor**:
     - Train R² Score: 0.9914885139106006
     - Test R² Score: 0.9332824523152341
   - **XGBoost**:
     - Train R² Score: 0.9749652568283947
     - Test R² Score: 0.9334154044335201

4. **Results**
The best-performing model was the XGBoost model, which achieved a test R² score of 0.9334154044335201. This indicates that the model is able to accurately predict CO(GT) levels using the available sensor data.

5. **Contributing**
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
