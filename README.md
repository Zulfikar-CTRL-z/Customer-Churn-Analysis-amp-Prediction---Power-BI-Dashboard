# Customer-Churn-Analysis-amp-Prediction---Power-BI-Dashboard
```

<img width="1302" height="732" alt="Screenshot 2026-09-15 165626" src="https://github.com/user-attachments/assets/5e20aac4-6750-4cf4-b89d-f0e48500d10f" />



📌 Project Overview
    This project focuses on analyzing customer churn for a
    Telecommunications company using Power BI. The goal is to identify key drivers of customer
    attrition, analyze customer demographics and tenure distribution,
    and provide actionable recommendations to boost customer retention.


🛠️ Tools & Technologies Used
    Power BI Desktop: Dashboard design, visual report building.
    Power Query: Data cleaning, handling null/missing values, data type transformations.
    DAX (Data Analysis Expressions): Custom measures (`Total Customers`, `Churned Customers`, `Churn Rate %`, `Tenure Bins`).


📊 Dashboard Key Components & Insights
1. Churn Rate Overview
    Total Customers: Evaluated total customer base.
    Churned Customers: Identified customers who left the service (`Churn = 'Yes'`).
    Churn Rate %: Calculated dynamic churn rate percentage using safe division.

2. Customer Demographics
    Gender & Family Status: Analyzed churn split across Gender, Partner status,
    and Dependents status using Donut and Bar charts.
    Key Insight: Single customers without partners/dependents show a higher propensity to churn.

3. Customer Tenure Analysis
    Tenure Bins: Grouped tenure into intervals (`0-1 Year`, `1-2 Years`, `2-4 Years`, `4+ Years`).
    Key Insight: High churn risk is concentrated in **new customers (0–12 months tenure)**. Retention increases significantly after 2 years.

4. Churn Drivers &amp; Business Factors
    Contract Type: Month-to-month contracts have the highest churn rate
    compared to 1-year and 2-year commitments.
    Payment Method: Electronic check users demonstrate a significantly higher churn
    rate compared to automated bank transfers or credit cards.
    Internet Service: Fiber Optic subscribers exhibit higher churn due to pricing/service expectations.


🧮 Key DAX Formulas Used

Total Customers = COUNTROWS('Telco_Customer_Churn_Dataset')

Churned Customers = 
CALCULATE(
    COUNTROWS('Telco_Customer_Churn_Dataset'),
    'Telco_Customer_Churn_Dataset'[Churn] = "Yes"
)

Churn Rate % = 
DIVIDE([Churned Customers], [Total Customers], 0)

Tenure Range = 
SWITCH(
    TRUE(),
    'Telco_Customer_Churn_Dataset'[tenure] &lt;= 12, "0-1 Year",
    'Telco_Customer_Churn_Dataset'[tenure] &lt;= 24, "1-2 Years",
    'Telco_Customer_Churn_Dataset'[tenure] &lt;= 48, "2-4 Years",
    "4+ Years"
)



💡 Strategic Recommendations
    1. Promote Long-Term Contracts: Offer incentives or discounted rates to shift Month-to-month subscribers into 1-Year or 2-Year plans.
    2. First-Year Onboarding: Focus retention programs and proactive support on customers in their first 12 months.
    3. Automated Billing Incentives: Encourage Electronic Check users to switch to auto-debit (Credit Card / Bank Transfer) to reduce churn.

