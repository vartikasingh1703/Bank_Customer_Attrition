# Customer Churn Prediction for XYZ Multinational Bank

## Overview
Customer retention is a fundamental aspect of any business, particularly for banks, where acquiring new customers can be significantly more costly than retaining existing ones. This project aims to predict customer churn for XYZ Multinational Bank by analyzing customer behavior and key attributes. By leveraging machine learning techniques, we aim to identify high-risk customers and suggest proactive measures to improve retention rates.

## 📂 Dataset Overview
https://www.kaggle.com/datasets/marusagar/bank-customer-attrition-insights/data
The dataset consists of customer details, including demographics, account features, and engagement levels. The target variable is Exited, where:

1 - Customer has left the bank.
0 - Customer remains with the bank.

Key Features:
- CreditScore - Customer's creditworthiness.
- Geography - Location of the customer.
- Gender - Customer's gender.
- Age - Customer's age.
- Tenure - Number of years with the bank.
- Balance - Account balance.
- NumOfProducts - Number of financial products held.
- HasCrCard - Whether the customer has a credit card.
- IsActiveMember - Engagement level with the bank.
- EstimatedSalary - Customer's estimated annual salary.
- Satisfaction Score - Rating based on service experience.
- Complain - Indicates if a customer has filed a complaint.
- Card Type - Type of credit card owned.
- Points Earned - Loyalty points accumulated.

## 🛠️ Step-by-Step Methodology

### 1️⃣ Data Preprocessing
- Load Dataset: Import the dataset using Pandas.
- Handle Missing Values: Check for and fill or drop missing values.
- Remove Unnecessary Columns: Drop `RowNumber`, `CustomerId`, and `Surname` as they don't contribute to churn prediction.
- Encoding Categorical Variables:
  - Convert `Geography`, `Gender`, and `Card Type` into numerical values using One-Hot Encoding.
- Feature Scaling:
  - Normalize numerical features like `CreditScore`, `Age`, `Balance`, etc., using StandardScaler.

### 2️⃣ Handling Imbalanced Data
- Use SMOTE (Synthetic Minority Over-sampling Technique):
  - Oversample the minority class to balance the dataset.

### 3️⃣ Model Selection & Training
- Split Data: Divide dataset into training (80%) and testing (20%) sets.
- Baseline Models: Train initial models including:
-    Model                   Mean Accuracy
     Logistic Regression      0.9984
     Decision Tree            0.9980
     Random Forest            0.9986
     XGBoost                  0.9986
   
- Hyperparameter Tuning:
  - We used GridSearchCV to fine-tune hyperparameters for better accuracy and 
    performance. The best hyperparameters improved the model's ROC-AUC score 
    significantly, achieving:
    - Random Forest  - 0.9992
    - XGBoost        - 0.9993

### 4️⃣ Model Evaluation
- Performance Metrics Used:
  - Accuracy
  - Precision, Recall, F1-score
  - Confusion Matrix
  - ROC-AUC Curve

### 5️⃣ Model Deployment
- Save the best model using `joblib`:
  ```python
  import joblib
  joblib.dump(best_rf, "churn_prediction_model.pkl")
  ```
- This allows reusing the trained model without retraining.

## 📊 Results & Insights
- Customers with lower tenure, lower credit scores, and fewer products are more likely to churn.
- Higher satisfaction scores and loyalty points reduce churn probability.
- Implementing personalized retention strategies based on these insights can improve customer loyalty.

## 🏆 Conclusion
This project demonstrates how machine learning can effectively predict customer churn, allowing banks to take proactive steps to improve retention. The use of **Random Forest with GridSearchCV** provided highly accurate predictions, and SMOTE helped handle class imbalance effectively.

## 📌 Future Work
- Implement deep learning models for further improvement.
- Deploy the model as a web application for real-time predictions.
- Integrate additional features like transaction history and social media sentiment analysis.

---
📢 Contributor: Vartika Singh

📧 Contact: 2001vartikasingh@gmail.com

🔗 GitHub: https://github.com/vartikasingh1703?tab=repositories

