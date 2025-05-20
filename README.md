# Bank Loan Decision Making Analytics

This project aims to automate the home improvement loan approval process using predictive modeling and customer segmentation. The dual objectives are (1) to predict loan defaults with interpretable models, and (2) to segment customers into risk profiles for targeted financial strategies.

## 🧠 Business Objectives

- **Automated Loan Default Prediction**  
  Predict whether an applicant is likely to default (`BAD = 1`) using models like Logistic Regression, Decision Tree, and Random Forest. The focus is on interpretability and compliance with the Equal Credit Opportunity Act.

- **Customer Segmentation for Risk Management**  
  Perform K-means and hierarchical clustering **separately on defaulters and non-defaulters** to discover actionable credit behavior patterns and create risk-based customer profiles.

## 📊 Dataset Overview

- **Total Observations**: 5,834
- **Target Variable**: `BAD` (1 = Default, 0 = No Default)
- **Key Features**: `DEBTINC`, `DELINQ`, `CLAGE`, `DEROG`, `YOJ`, `LOAN`, etc.
- **Missing Values**: Handled via median imputation, KNN imputation, and mode replacement.

## 🔍 Feature Engineering & Selection

- Feature Importance via **Random Forest** and **LASSO**
- Top Predictors: `DEBTINC`, `DELINQ`, `DEROG`, `CLAGE`, `NINQ`
- Variables transformed using scaling (Z-score) for clustering; original scales retained for classification

## 🤖 Classification Models & Performance

| Model              | Accuracy | Sensitivity | Specificity | F1 Score |
|--------------------|----------|-------------|-------------|----------|
| Logistic Regression| 84.86%   | 34.67%      | 96.22%      | 0.458    |
| Decision Tree      | 89.14%   | 69.04%      | 93.69%      | 0.701    |
| Random Forest      | 93.03%   | 71.83%      | 97.83%      | 0.792    |

> **Best Model**: Random Forest (high accuracy and balanced recall)

## 🔗 Clustering Strategy

- **Separated Clustering**:  
  - Defaulters (`BAD = 1`)  
  - Non-defaulters (`BAD = 0`)
- **Techniques Used**: K-means, Hierarchical Clustering
- **Optimal K**: Determined via Elbow & Silhouette Methods; final K = 3
- **Segment Descriptions**:
  - **Defaulter Clusters**:  
    1. High debt and delinquencies  
    2. Derogatory reports  
    3. Inconsistent payers
  - **Non-Defaulter Clusters**:  
    1. Ideal borrowers  
    2. Moderate-risk but stable  
    3. Emerging credit builders

## 📁 Recommended Repo Structure

```
bank-loan-default-analytics/
├── code/
│   └── R-file-5-1.R
├── data/
│   └── Loan.csv
├── Home Improvement Loan for Students.docx
├── presentation-project2.pptx
├── project 2 - Subash Yadav-2.docx
└── project 2 - Subash Yadav-2.pdf

```

## 🧾 Techniques Used

- SMOTE for class imbalance
- Logistic Regression for transparency
- Random Forest for performance
- LASSO and Random Forest for feature selection
- K-means and Hierarchical clustering for segmentation
- PCA **not used** to retain interpretability

## 📌 Key Takeaways

- Random Forest showed **best performance** with 93% accuracy.
- Debt-to-Income Ratio, Derogatory Reports, and Delinquencies are **top predictors**.
- Separate clustering for defaulters and non-defaulters enables **granular risk segmentation**.

## 👨‍💻 Author

**Subash Yadav**  
[LinkedIn](https://www.linkedin.com/in/mathachew7)  
[GitHub](https://github.com/mathachew7)
