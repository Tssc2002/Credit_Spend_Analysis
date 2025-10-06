# 📊 Predicting Credit Consumption — Capstone Project  

## 🧩 Overview  
This project aims to **predict the average credit card consumption** of customers for the next three months, using demographic and behavioral data from a leading bank.  
By leveraging **machine learning models**, the goal is to help the bank understand spending patterns, identify high-value customers, and optimize marketing strategies.

---

## 🏦 Business Context  
The credit card industry generates vast amounts of customer data daily. Understanding **how customers spend** and **what drives their credit consumption** can help banks improve **customer relationship management (CRM)**, design **targeted marketing campaigns**, and increase **revenue through retention and upselling**.  

---

## 🎯 Business Objectives  
The project focuses on:  
1. Building a predictive model to estimate **credit card consumption** for the next 3 months.  
2. Identifying **key drivers** behind spending behavior.  
3. Providing **insightful visualizations** to assist business decisions.

---

## 🧾 Data Description  

The dataset includes three CSV files:  

### 1. **CustomerDemographics.csv**  
Contains demographic details such as:  
- `ID`: Customer unique identifier  
- `Account_type`: Savings/Current  
- `Gender`, `Age`, `Income`  
- `Emp_Tenure_Years`: Years of employment  
- `Tenure_with_Bank`: Relationship duration with the bank  
- `Region_code`, `NetBanking_Flag`, `Avg_days_between_transaction`

### 2. **CustomerBehaviorData.csv**  
Includes behavioral and transactional details:  
- Credit/Debit spend for April–June (`CC_cons_apr`, `DC_cons_may`, etc.)  
- Transaction counts (`CC_count_apr`, `DC_count_jun`, etc.)  
- Loan and investment indicators (`Personal_loan_active`, `Investment_1`, etc.)  
- Account balance movements (`Credit_amount_apr`, `Debit_amount_jun`, etc.)  
- Loan enquiry and EMI flags (`Loan_enq`, `Emi_active`)  

### 3. **CreditConsumptionData.csv**  
- `ID`: Customer ID  
- `cc_cons`: **Target variable** — Average Credit Card Spend for the next 3 months  

---

## 🧠 Problem Statement  
Some customers have missing values for `cc_cons`.  
The task is to **predict these missing values** using regression techniques trained on customers with existing consumption data.

---

## ⚙️ Methodology  

### 🔍 1. Data Preprocessing  
- Handled missing values and outliers  
- Merged multiple datasets on `ID`  
- Feature engineering to create meaningful metrics (e.g., total monthly spend, spend ratio, loan activity score)  
- Scaled numerical variables and encoded categorical features  

### 📊 2. Exploratory Data Analysis (EDA)  
- Distribution analysis for numeric variables  
- Spending pattern visualization by **income level, age, and account type**  
- Correlation heatmaps to identify key drivers  
- Relationship between **loans, EMIs, and spending trends**

### 🤖 3. Model Building  
Multiple regression algorithms were tested:  
- Linear Regression  
- Ridge & Lasso Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- XGBoost  

Model performance was compared using **Root Mean Square Percentage Error (RMSPE)**.

### 📈 4. Model Evaluation  
- Split data into training (70%) and test (30%)  
- Used **cross-validation** to validate generalization  
- Selected the model with the lowest RMSPE and strong interpretability  

### 📉 5. Predictions  
Predicted the missing `cc_cons` values for customers using the best-performing model.

---

## 📊 Evaluation Metric  
**Root Mean Square Percentage Error (RMSPE)** was used to validate model accuracy:  

\[
RMSPE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} \left( \frac{y_i - \hat{y}_i}{y_i} \right)^2}
\]

---

## 💡 Key Insights  
- **Income** and **Employment Tenure** are major predictors of credit spending.  
- Customers with **active loans** tend to spend more on credit cards, possibly indicating credit dependence.  
- **Digital customers (NetBanking_Flag = Yes)** exhibit higher and more consistent spending.  
- Regional differences indicate targeted marketing potential.  

---

## 📁 Repository Structure  

```
📦 Predicting_Credit_Consumption
│
├── 📘 Predicting_Credit_Consumption_Capstone.ipynb     # Complete ML notebook (EDA + Modeling)
├── 📗 Capstone Project - ML-PredictingCreditConsumption.pdf  # Project documentation
├── 📄 README.md                                         # Project overview
├── 📂 data/
│   ├── CustomerDemographics.csv
│   ├── CustomerBehaviorData.csv
│   ├── CreditConsumptionData.csv
│
└── 📂 outputs/
    ├── predicted_credit_consumption.csv                 # Predicted missing values
    ├── model_performance_summary.csv                    # RMSPE comparison
```

---

## 🧰 Tech Stack  
- **Language:** Python 3  
- **Libraries:**  
  `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`  
- **Environment:** Jupyter Notebook  

---

## 🚀 How to Run  

1. Clone the repository  
   ```bash
   git clone https://github.com/<your-username>/Predicting_Credit_Consumption.git
   cd Predicting_Credit_Consumption
   ```

2. Install dependencies  
   ```bash
   pip install -r requirements.txt
   ```

3. Open and run the Jupyter Notebook  
   ```bash
   jupyter notebook Predicting_Credit_Consumption_Capstone.ipynb
   ```

4. View model predictions in `outputs/predicted_credit_consumption.csv`

---

## 📌 Future Enhancements  
- Deploy the model as an **interactive Streamlit dashboard**  
- Integrate with **bank CRM systems** for real-time predictions  
- Explore **AutoML pipelines** for hyperparameter optimization  

---

## 🧾 Author  
**Sri Sai Chowadry Thati**  
*Certified Data Analyst (AnalytixLabs)*  
📧 srisaichowdary1210@gmail.com
📍 India  
