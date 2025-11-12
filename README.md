# Telecom-Customer-Churn-PowerBI
“Power BI dashboard analyzing customer churn in the telecom industry”
# 📊 Telecom Customer Churn Analysis – Power BI Project

This Power BI project analyzes **customer churn** in a telecom company.  
It identifies which customers are leaving (churn), why they’re leaving, and what factors most strongly influence their decision — enabling the company to improve retention and revenue.

---

## 🚀 Project Overview

**Goal:**  
To understand the patterns behind customer churn and create actionable insights for business decision-making.

**Objectives:**
- Analyze overall **customer churn rate**
- Identify **key factors** that influence churn
- Segment customers by **demographics and service usage**
- Visualize **revenue impact** and retention opportunities

---

## 🧩 Dataset Overview

**File used:** `Telco_Customer_Churn_Dataset.xlsx`

This dataset contains information about a telecom company’s customers, their account details, services subscribed, and whether they have churned or not.

### Key Columns:
| Column | Description |
|---------|-------------|
| `customerID` | Unique ID assigned to each customer |
| `gender` | Male / Female |
| `SeniorCitizen` | 1 if customer is a senior citizen, else 0 |
| `Partner` | Whether the customer has a partner |
| `Dependents` | Whether the customer has dependents |
| `tenure` | Number of months the customer has stayed with the company |
| `PhoneService` | Whether the customer has phone service |
| `InternetService` | Type of internet service (DSL, Fiber optic, None) |
| `Contract` | Contract type (Month-to-month, One year, Two year) |
| `PaymentMethod` | Customer's payment method |
| `MonthlyCharges` | Amount charged monthly |
| `TotalCharges` | Total amount billed to the customer |
| `Churn` | Whether the customer has left the company |

**Source:** [Telco Customer Churn Dataset – Kaggle](https://www.kaggle.com/blastchar/telco-customer-churn)

---

## 📈 Dashboard Summary

The Power BI report is organized into multiple interactive pages:

### 1️⃣ **Overview Dashboard**
- Displays total customers, churn count, churn rate, and total revenue.
- Includes KPIs and churn trends over time.

### 2️⃣ **Customer Demographics**
- Analyzes churn based on gender, senior citizen status, and partner/dependent status.

### 3️⃣ **Contract & Payment Analysis**
- Shows churn by contract type, tenure, and payment method.

### 4️⃣ **Services Overview**
- Explores churn by internet and phone services.

---

## 🧠 Key Insights

- **Overall churn rate:** ~26%
- Customers with **Month-to-Month contracts** are more likely to churn.
- **Electronic check** payment method has the highest churn.
- **Fiber optic** users churn more than DSL users.
- **Senior citizens** and **short-tenure customers** show higher churn.
- Customers with **longer contracts** and **auto-payment** methods are more loyal.

---

## 🧮 DAX Measures Used

```DAX
Churn Rate =
DIVIDE(
    CALCULATE(COUNTROWS(CustomerData), CustomerData[Churn] = "Yes"),
    COUNTROWS(CustomerData)
)

Total Customers = COUNTROWS(CustomerData)

Revenue Lost =
CALCULATE(
    SUM(CustomerData[MonthlyCharges]),
    CustomerData[Churn] = "Yes"
)

Average Tenure = AVERAGE(CustomerData[tenure])

🧾 Conclusion

This Telecom Customer Churn Analysis project provided a clear picture of customer behavior and the factors driving churn.
By analyzing demographics, contracts, and payment preferences, we discovered that:

Short-term, flexible contracts lead to higher churn.

Automating payments and promoting longer-term plans can reduce churn.

Customer tenure is a strong indicator of loyalty — early retention efforts are essential.

Targeted offers for high-risk groups (e.g., month-to-month or electronic check users) can significantly improve retention.

Business Recommendation:
Telecom companies should focus on:

Encouraging long-term contracts

Offering discounts or loyalty rewards for early customers

Promoting automatic payment methods

Providing better support and service reliability for Fiber optic users

By implementing these strategies, the company can reduce churn, improve satisfaction, and maximize lifetime customer value.


