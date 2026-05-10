# Predicting House Prices in a Messy Market

This project focuses on building a machine learning pipeline to predict house prices using the Ames Housing dataset. The workflow covers data preprocessing, exploratory data analysis (EDA), feature engineering, scaling, model training, cross-validation, and final prediction generation.

## Project Workflow

* Filtered dataset to retain only numerical features
* Performed EDA using correlation analysis, heatmaps, scatterplots, and histograms
* Handled missing values using median imputation and logical replacements
* Engineered new features such as:
    * TotalSF
    * TotalBathrooms
    * HouseAge
* Applied log transformation to the target variable (SalePrice) to reduce skewness
* Scaled features using StandardScaler
* Trained and evaluated:
    * Linear Regression
    * Ridge Regression
* Tuned Ridge Regression using different alpha values
* Generated predictions on a held-out test dataset and prepared a submission file

## Tools and Libraries

* Python
* Pandas
* NumPy
* Matplotlib / Seaborn
* Scikit-learn

## Model Performance
Ridge Regression produced better generalization performance than standard Linear Regression, with the best result achieved at **alpha = 50**.

## Errors Noticed in First Submission
1. **Data Leakage During Cross-Validation**
    * A Pipeline containing scaling and regression was created, but cross_validate() was run on the already scaled data (X_train_scaled) using model instead of pipeline.
    * This caused leakage because scaling was performed before cross-validation.
2. **Final Model Was Not Trained on Full Dataset**
    * The model was trained only on X_train_scaled and y_train.
    * Ideally, the final model should be retrained on the entire processed dataset before making test predictions.
