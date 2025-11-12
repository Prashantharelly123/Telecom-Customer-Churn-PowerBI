# Telecom-Customer-Churn-PowerBI
“Power BI dashboard analyzing customer churn in the telecom industry”
# 📊 Telecom Customer Churn Analysis – Power BI Project

This project analyzes **customer churn behavior** for a telecom company using **Power BI**.  
It transforms raw customer data into **interactive dashboards** that reveal churn patterns, customer profiles, and actionable business insights.

---

## 🎯 Project Objectives

- Analyze customer churn patterns and identify key factors influencing attrition.  
- Understand customer behavior based on **demographics, service subscriptions,** and **billing information**.  
- Measure **churn rate** across customer segments like contract type, internet service, and payment method.  
- Visualize business performance through **Power BI dashboards** and key KPIs.  
- Provide insights to support **data-driven retention strategies** and improve **customer satisfaction**.

---

## 🧩 Dataset Overview

**Dataset Name:** Telco Customer Churn Dataset  
**Source:** [Kaggle – Telco Customer Churn](https://www.kaggle.com/blastchar/telco-customer-churn)  
**File Type:** Excel  
**Records:** 7,043 customers  
**Columns:** 21 fields  

### Key Columns
| Column | Description |
|---------|-------------|
| `customerID` | Unique customer identifier |
| `gender`, `SeniorCitizen`, `Partner`, `Dependents` | Demographic features |
| `tenure` | Number of months customer has stayed |
| `PhoneService`, `InternetService`, `StreamingTV`, `TechSupport` | Service subscriptions |
| `Contract` | Contract type (Month-to-month, One year, Two year) |
| `PaymentMethod` | Mode of payment (Credit Card, Electronic Check, etc.) |
| `MonthlyCharges`, `TotalCharges` | Billing data |
| `Churn` | Indicates if the customer has left (Yes/No) |

---

## 🧹 Data Preparation

Performed in **Power Query Editor** in Power BI:
- Imported dataset from Excel.
- Cleaned and standardized data.
- Removed nulls and blanks from `TotalCharges` column.
- Converted `TotalCharges` from text to numeric.
- Created calculated columns and DAX measures:
  - **Churn Rate**
  - **Average Monthly Charges**
  - **Average Tenure**
  - **Total Revenue**
- Standardized categorical values (e.g., “No internet service” → “No”).
- Added derived metrics such as **Total Services Subscribed**.
- Ensured data validation with no duplicates or mismatches.

---

## 📊 Power BI Dashboards

### 1️⃣ Customer Demographics Dashboard
**Visuals Used:**
- Donut Chart → Gender distribution  
- Bar Chart → Senior Citizen vs. Non-senior churn  
- Column Chart → Tenure segmentation  
- Line Chart → Churn rate across tenure  
- Cards → Total Customers, Churned Customers, Churn Rate, Avg. Tenure  

**Purpose:** Understand churn behavior across different customer groups.

---

### 2️⃣ Service Subscription Dashboard
**Visuals Used:**
- Stacked Column → Phone & Internet service usage  
- Funnel Chart → Churn by Internet Service Type (DSL, Fiber, None)  
- Clustered Bar → Add-on service usage  
- Scatter Plot → Number of services vs. churn  
- Slicers → Gender, Senior Citizen, Internet Service, Contract Type  

**Purpose:** Identify how service combinations impact churn.

---

### 3️⃣ Contract & Billing Dashboard
**Visuals Used:**
- Bar Chart → Churn by Contract Type  
- Donut Chart → Payment Method distribution  
- Clustered Column → Avg. Total Charges by Contract Type  
- Line Chart → Monthly Charges by Payment Method  
- Table/Matrix → Billing KPIs by Contract Type  

**Purpose:** Analyze contract types and billing methods influencing churn.

---

## 🧠 Key Insights

- **Overall churn rate:** ~26%
- **Month-to-month contracts** have the highest churn.
- Customers paying via **electronic check** churn most frequently.
- **Fiber optic** service users churn more than DSL users.
- **Senior citizens** and **new customers (short tenure)** have higher churn.
- Customers with **multiple service subscriptions** and **longer contracts** are more loyal.
- Average **monthly charge** and **total charge** are higher among churned customers.

---

## 📈 DAX Measures

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
```

---

## 💡 Business Applications

- **Marketing Teams:** Identify and target high-risk customers with personalized retention offers.  
- **Customer Support:** Prioritize service improvements for segments with high churn.  
- **Management:** Track churn KPIs for strategic planning and performance monitoring.  
- **Product Teams:** Optimize bundles and pricing models for long-term retention.

---

## 🧾 Recommendations

- Encourage **long-term contracts** (1-year or 2-year plans) through discounts or loyalty rewards.  
- Promote **bundled service packages** (Internet + Streaming + Security).  
- Offer **personalized retention offers** for senior citizens and high-charge users.  
- Educate customers on **online backup** and **device protection** benefits.  
- Closely monitor **payment issues** and **monthly charge increases** as churn indicators.

---

## 🏁 Conclusion

The Power BI dashboards provide a **clear and interactive view** of customer churn behavior.  
The analysis revealed that **high monthly charges**, **month-to-month contracts**, and **fiber optic services** are major churn drivers.  
Customers with **longer tenure**, **multiple services**, and **stable payment methods** show higher loyalty.

By implementing these insights, telecom companies can:
- Reduce churn through **targeted retention strategies**
- Improve **customer satisfaction and loyalty**
- Boost **revenue stability** and **long-term profitability**

**Final Takeaway:**  
This project demonstrates how Power BI can turn raw telecom data into actionable business intelligence — empowering teams to make data-driven decisions that reduce churn and drive growth.






