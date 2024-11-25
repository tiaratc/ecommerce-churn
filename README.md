
# E-Commerce Customer Churn Prediction

## Project Overview
This project focuses on predicting customer churn in an e-commerce platform, Ezora based in India, using machine learning techniques. **Customer churn**, in this context, refers to customers who are no longer engaging with the platform (defined as `Churn = 1`). By identifying these customers early, the business can proactively implement retention strategies, such as personalized incentives or improved customer experiences, to reduce churn rates and maintain profitability.

The primary goal of this project is to build a robust predictive model while minimizing **false negatives (FN)**. This ensures that customers at risk of churning are accurately identified, allowing the business to focus retention efforts effectively. The evaluation metric chosen is the **F2 score**, which places greater emphasis on recall over precision.

---

## Key Objectives
1. **Understand Churn**:
   - Analyze customer behavior to define what drives churn in this dataset.
   - Investigate patterns such as low tenure, complaints, and cashback incentives.

2. **Handle Class Imbalance**:
   - Address the imbalance in the `Churn` label using techniques like **SMOTE**, **SMOTE Tomek**, and hybrid methods to improve model performance.

3. **Optimize Model Performance**:
   - Tune models such as LightGBM using `RandomizedSearchCV` and focus on achieving an **F2 score** of at least 0.85 on the training data.

4. **Insights and Recommendations**:
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

### 3. Model Development
- Train multiple machine learning models, including LightGBM, with hyperparameter tuning via `RandomizedSearchCV`.
- Incorporate the model into a pipeline that integrates preprocessing and evaluation seamlessly.
  
### 4. Model Evaluation
- Evaluate models using the **F2 score** to prioritize recall.
- Analyze **ROC-AUC** and **Precision-Recall curves** for further performance insights.

---

### Best Model:
	•	The LightGBM classifier achieved the best performance:
	•	F2 Score: 84%
	•	Recall: 88%
	•	Precision: 70%
	•	The model effectively identifies most churn-risk customers, while managing false positives.

## Business Impact

Key Achievements of the ML Model for Ezora

	1.	Cost Efficiency:
	•	Machine learning enables Ezora to save 79.2% of promotional costs, optimizing resource allocation.
	2.	Increased Net Savings:
	•	The implementation of the ML model resulted in net savings of INR 332,300, a significant boost to financial performance.
	3.	Controlled Costs:
	•	Total cost of implementing the ML model, including promotional costs and potential losses from false negatives, was kept at:
INR 170,600
	4.	Outstanding ROI:
	•	Achieved a Return on Investment (ROI) of 194.8%, demonstrating the strong financial impact and viability of the ML model.
	5.	Strategic Reinvestment Opportunity:
	•	The savings generated provide Ezora with the ability to reinvest in strategic initiatives, fostering long-term growth and sustainability.
