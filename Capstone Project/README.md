# Loan Default Prediction Using Machine Learning

## Project Overview

This project focuses on predicting loan default risk using machine learning techniques. The objective is to identify borrowers who are likely to default on their loans, enabling financial institutions to make better lending decisions and reduce credit risk.

The project was completed as an **Advanced Depth Track Capstone Project** and combines both supervised and unsupervised learning approaches to generate predictive and business-focused insights.


---

## Business Problem

Loan defaults can lead to significant financial losses for lending institutions. Accurately identifying high-risk borrowers before loan approval helps:

* Reduce financial losses
* Improve credit risk management
* Support better lending decisions
* Enhance portfolio performance

The goal of this project is to build machine learning models capable of predicting borrower default risk while providing actionable business insights.

---

## Dataset

**Source:** Kaggle Loan Default Dataset

The dataset contains borrower-related information including:

* Age
* Income
* Loan Amount
* Loan Term
* Credit Score
* Education Level
* Employment Status
* Marital Status
* Number of Dependents
* Loan Purpose
* Interest Rate
* Default Status (Target Variable)

---

## Project Workflow

### 1. Data Collection and Loading

* Downloaded the dataset from Kaggle
* Loaded data into a Pandas DataFrame
* Stored data in SQLite for SQL-based exploration and querying

### 2. Exploratory Data Analysis (EDA)

Performed exploratory analysis to:

* Understand dataset structure
* Examine variable distributions
* Identify relationships between features
* Analyze loan default patterns
* Detect potential data quality issues

Visualizations were created using:

* Matplotlib
* Seaborn

---

## Feature Engineering

Several new features were created to improve model performance:

### Credit Score Categories

Borrowers were grouped into risk categories based on credit scores.

### Income Groups

Income levels were segmented into meaningful categories.

### Loan Burden Categories

Loan burden was calculated to assess repayment pressure.

### Age Groups

Borrowers were categorized by age ranges.

### Loan Term Categories

Loan durations were grouped into meaningful intervals.

### Loan-to-Income Ratio

A financial risk indicator measuring loan size relative to income.

### Debt-to-Income and Credit Score Interaction

An interaction feature designed to capture combined risk behavior.

---

## Data Preprocessing

### Encoding

Categorical variables were transformed using:

* Label Encoding
* One-Hot Encoding

### Feature Scaling

Numerical variables were standardized using:

* StandardScaler

---

## Unsupervised Learning: K-Means Clustering

To better understand borrower segments, K-Means clustering was applied.

### Cluster Evaluation

The optimal number of clusters was determined using:

* Elbow Method
* Silhouette Analysis

### Cluster Interpretation

Cluster profiling was performed to identify differences among borrower groups.

### PCA Visualization

Principal Component Analysis (PCA) was used to visualize clusters in two dimensions.

### Key Finding

Cluster 0 emerged as the highest-risk borrower segment, with a default rate of approximately **20.48%**, significantly higher than the overall dataset default rate of **11.6%**.

---

## Supervised Learning: Classification Models

Three classification algorithms were trained and evaluated:

### Logistic Regression

A baseline model used for binary classification and interpretability.

### Decision Tree Classifier

Used to capture non-linear relationships and borrower behavior patterns.

### Random Forest Classifier

An ensemble learning method designed to improve prediction accuracy and reduce overfitting.

---

## Handling Class Imbalance

The dataset exhibited a significant imbalance between defaulters and non-defaulters.

### Approach 1: Class Weighting

Model weights were adjusted to give greater importance to the minority class.

### Approach 2: Threshold Tuning

Classification probability thresholds were modified to improve detection of defaulters.

---

## Model Evaluation

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC
* Confusion Matrix

---

## Results

### Best Model

**Random Forest with Class Weighting**

Key performance highlights:

* Recall: **0.638**
* ROC-AUC: **0.751**
* Accuracy: **0.724**

Although the baseline Random Forest achieved higher accuracy (0.886), it failed to identify most actual defaulters. The class-weighted Random Forest was selected because it provided a better balance between predictive performance and business value.

---

## Business Insights

### High-Risk Borrower Segment

Clustering analysis revealed a borrower segment with substantially higher default risk.

This group may require:

* Enhanced monitoring
* Stricter credit assessment
* Specialized risk management strategies

### Model Deployment Recommendation

Deploy the **Class-Weighted Random Forest Model** because:

* It identifies more actual defaulters.
* It aligns better with business objectives.
* It minimizes the risk of approving borrowers likely to default.

---

## Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

### Database

* SQLite

### Machine Learning Techniques

* K-Means Clustering
* Principal Component Analysis (PCA)
* Logistic Regression
* Decision Tree
* Random Forest

---

## Future Improvements

Potential enhancements include:

* Advanced feature engineering
* Hyperparameter optimization
* Cross-validation
* Additional ensemble models
* Cost-sensitive learning
* External data integration
* Deployment as a web application or API

---

## Conclusion

This project demonstrates how machine learning can be used to predict loan defaults and support credit risk management. By combining clustering and classification techniques, the solution provides both predictive accuracy and valuable business insights that can help financial institutions make more informed lending decisions.
