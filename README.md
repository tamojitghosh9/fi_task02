# fi_task02
Future Interns - Data Science &amp; Analytics - 2026 - Task 2

Task details --- Analyze customer data to identify churn patterns, key retention drivers,
and customer lifetime trends for a subscription-based business.

dataset used - https://www.kaggle.com/datasets/blastchar/telco-customer-churn

tools used - Microsoft Excel (to clean and analyze the data), Microsoft PowerBi (to create the churn analysis report)

actions :-

- data transform (checking for null/invalid values, changing data type where required, etc.)

- changed the values of SeniorCitizen column from (1,0) to (Yes, No)

- added new columns:

  i) 'Tenure Bucket' --- 0-1years for tenure<12 months, 1-2years for tenure<24 months, and so on

  ii) 'Total Services' --- summation of the number of services availed by a customer

  iii) 'MonthlyCharges (bins)' --- 60 for 60-69, 70 for 70-79, and so on

- created new measures:

  i) Active Customers = [Total Customers] - [Churned Customers]

  ii) Avg Monthly Charges = AVERAGE('WA_Fn-UseC_-Telco-Customer-Churn (1)'[MonthlyCharges])

  iii) Churn Rate % = DIVIDE([Churned Customers], [Total Customers], 0)

  iv) Churned Customers = 
      CALCULATE(
      [Total Customers], 
      'WA_Fn-UseC_-Telco-Customer-Churn (1)'[Churn] = "Yes")

  v) Total Customers = COUNTROWS('WA_Fn-UseC_-Telco-Customer-Churn (1)')

- created new table to include in report:

  Table name - Strategic_Targets

  Fields - i) Strategic Goal   ii) KPI to track   iii) Target Outcome

NOTE: Open the .pbix file, go to the dashboard/report view and use the interactive charts and graphs to view the data in a structured and categorized format, according to your wish. Use the dropdown slicers to filter out results and see required information.
