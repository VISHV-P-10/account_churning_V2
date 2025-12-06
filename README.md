Churn Prediction using Logistic Regression:
A complete machine learning mini-project that predicts whether a bank customer will churn (leave the bank) using Logistic Regression.
This project covers end-to-end ML workflow including EDA, preprocessing, model training, and hyperparameter tuning.

project insight:

Logistic Regression (Binary Classification)
Exploratory Data Analysis (EDA)
Correlation Heatmap
One-Hot / Label Encoding
Train–Test Split
Feature Scaling (Standardization)
Model Training + Accuracy Score
Model Coefficients Interpretation
Hyperparameter Tuning (λ / C)

 Dataset Info:

Dataset: Bank Customers
Key Columns
CreditScore
Country
Gender
Age
Tenure
Balance
NumOfProducts
HasCrCard
IsActiveMember
EstimatedSalary

Exited → (Target: 1 = churned, 0 = not churned)

Goal: Predict whether a customer will churn.

About Churn:
Churn → when a customer closes their bank account.
Exited = 1 → Customer churned
Exited = 0 → Customer stayed

Logistic Regression is perfect here because the output is binary (0/1).

 Exploratory Data Analysis (EDA):
 Correlation Heatmap:
Light colors → high correlation
Dark colors → low correlation
Age shows the strongest correlation with churn
Balance, Salary, Credit Score have weaker correlation

 Box Plot (Age vs Churn):
Older customers churn more often
Median age of churners is higher

 Gender vs Churn:
Females churn more than males

Shown using bar plot

 One-Hot / Label Encoding
Why encoding?
ML models can’t understand text categories.

Encoding gender:
Male   → 1  
Female → 0

For multiple categories:
Male:       1 0 0  
Female:     0 1 0  
Trans:      0 0 1

 Feature Selection:
Features (X):
CreditScore
Age
Tenure
Balance
NumOfProducts
HasCrCard
IsActiveMember
EstimatedSalary
Gender (encoded)
Target (y):
Exited

Train–Test Split:
      test_size = 0.2  
      → 80% training  
      → 20% testing

Standard Scaling:
               Used because features are on different scales (e.g., Salary ≈ 100000, Age ≈ 40).

Formula:
          (x – mean) / std
          Scaling improves model stability and performance.

Logistic Regression — Model Training

Steps:

   Import LogisticRegression
   Fit on training data
   Measure accuracy using .score()

Initial Accuracy: ~0.80 (80%)

Model Coefficients

Coefficients show which features increase or decrease churn probability.

High positive value → increases churn risk

High negative value → decreases churn risk

Age has strong positive weight → important
Balance generally has low weight → less impact

Hyperparameter Tuning (λ / C)

In sklearn:

C = 1 / λ

Strategy:

Loop λ from 0.01 → 100 with step 0.1

For each λ:

Train model

Compute accuracy

Store results

Plot scores

Pick best λ value

Best Results

Best λ ≈ 6.24

Best Accuracy ≈ 0.744

Improved from 80% → 81.55%

🏁 Final Model

Trained using the best λ value:

C = 1 / λ_best


Final Accuracy: ~81.55%

💼 Business Insight

This model helps banks identify customers who are likely to churn.
They can then:

Call customers

Offer benefits

Provide incentives

Improve customer satisfaction

Ultimately → reduces customer loss and increases revenue.
