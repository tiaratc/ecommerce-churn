
# E-Commerce Customer Churn Prediction

## Project Overview
This project focuses on predicting customer churn in an e-commerce platform using machine learning techniques. **Customer churn**, in this context, refers to customers who are no longer engaging with the platform (defined as `Churn = 1`). By identifying these customers early, the business can proactively implement retention strategies, such as personalized incentives or improved customer experiences, to reduce churn rates and maintain profitability.

The primary goal of this project is to build a robust predictive model while minimizing **false negatives (FN)**. This ensures that customers at risk of churning are accurately identified, allowing the business to focus retention efforts effectively. The evaluation metric chosen is the **F2 score**, which places greater emphasis on recall over precision.

---

## Key Objectives
1. **Understand Churn**:
   - Analyze customer behavior to define what drives churn in this dataset.
   - Investigate patterns such as low tenure, complaints, and cashback incentives.

2. **Handle Class Imbalance**:
   - Address the imbalance in the `Churn` label using techniques like **SMOTE**, **Tomek Links**, and hybrid methods to improve model performance.

3. **Feature Engineering**:
   - Explore transformations like Power Transformer and feature interactions to enhance the predictive power of the model.

4. **Optimize Model Performance**:
   - Tune models such as LightGBM using `RandomizedSearchCV` and focus on achieving an **F2 score** of at least 0.85 on the training data.

5. **Insights and Recommendations**:
   - Provide actionable insights based on the model predictions, highlighting key factors driving churn.

---

## Dataset Summary
The dataset includes 3,941 records with the following features:
- **Tenure**: Duration (in months) the customer has been associated with the platform.
- **WarehouseToHome**: Distance from the warehouse to the customer’s home.
- **SatisfactionScore**: A score representing customer satisfaction.
- **NumberOfDeviceRegistered**: Number of devices registered by the customer.
- **DaySinceLastOrder**: Days since the customer last placed an order.
- **CashbackAmount**: Total cashback amount received by the customer.
- **Churn**: Target variable (`1` for churned, `0` for retained).

Key observations:
- Churned customers tend to have significantly **lower tenure**, fewer cashback amounts, and slightly better satisfaction scores.

---

## Methodology
### 1. Data Preprocessing
- Handle missing values in features such as `Tenure` and `DaySinceLastOrder`.
- Normalize numerical features to reduce skewness.

### 2. Class Imbalance Mitigation
- Implement sampling techniques (e.g., **SMOTE**, **Tomek Links**) to balance the `Churn` labels.

### 3. Feature Engineering
- Generate interaction features to capture complex relationships.
- Transform skewed data using techniques like Power Transformer.

### 4. Model Development
- Train multiple machine learning models, including LightGBM, with hyperparameter tuning via `RandomizedSearchCV`.
- Incorporate the model into a pipeline that integrates preprocessing and evaluation seamlessly.

### 5. Model Evaluation
- Evaluate models using the **F2 score** to prioritize recall.
- Analyze **ROC-AUC** and **Precision-Recall curves** for further performance insights.

---

## Results
- Achieved an **F2 score of ≥0.85** on the training data with the tuned LightGBM model.
- Key drivers of churn identified include **low tenure**, **lower cashback amounts**, and **recent inactivity**.

---

## Business Impact
By minimizing false negatives, this project helps the e-commerce platform:
1. Retain customers with targeted interventions.
2. Improve customer lifetime value (CLV).
3. Optimize retention strategies by identifying churn patterns.

---

## Future Work
- Implement advanced feature selection techniques to improve model interpretability.
- Deploy the model as an API to integrate with the platform’s CRM system for real-time churn prediction.
