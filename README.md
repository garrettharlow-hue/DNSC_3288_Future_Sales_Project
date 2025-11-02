# Predict Future Sales
**Basic Information**
- Collaborators: Garrett (garrett@acme.com), Brooke (brooke@acme.com), Khadija (khadija@acme.com), Henry (henry@acme.com), Chris (chris@acme.com)
- Model Date: November, 2025
- Model Version: 1.0
- License: Apache 2.0
- Model Implementation Code:https://colab.research.google.com/drive/10djDrUJCI6xkbuIELrcJSlnEHHzZK3ou?usp=sharing

**Intended Use**
- Intended Uses: Predicting sales volumes and forecasting the amount of sales in the next month for each store and product to assist with inventory and supply chain planning. This model can support retail decision making and demand planning for variosu retail stores and product lines. 
- Intended Users: Data Analysts, Supply Chain Analysts, Retail Operations Managers, E-Commerce Retailers
- Out-of-Scope Uses: Predicting sales for new stores, predicting individual customer purchases, using the data to address the financial standing of the company. 

**Training Data**
- Source of training data: Kaggle, https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales/overview
- How training data was divided into training and validation data:
- Number of rows in training and validation data:
    - Rows in trained data:
    - Rows in validation data: 
* Data dictionary: 

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**ID**| ID | int | unique row indentifier |
| **LIMIT_BAL** | input | float | amount of previously awarded credit |
| **SEX** | demographic information | int | 1 = male; 2 = female
| **RACE** | demographic information | int | 1 = hispanic; 2 = black; 3 = white; 4 = asian |
| **EDUCATION** | demographic information | int | 1 = graduate school; 2 = university; 3 = high school; 4 = others |
| **MARRIAGE** | demographic information | int | 1 = married; 2 = single; 3 = others |
| **AGE** | demographic information | int | age in years |
| **PAY_0, PAY_2 - PAY_6** | inputs | int | history of past payment; PAY_0 = the repayment status in September, 2005; PAY_2 = the repayment status in August, 2005; ...; PAY_6 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; ...; 8 = payment delay for eight months; 9 = payment delay for nine months and above |
| **BILL_AMT1 - BILL_AMT6** | inputs | float | amount of bill statement; BILL_AMNT1 = amount of bill statement in September, 2005; BILL_AMT2 = amount of bill statement in August, 2005; ...; BILL_AMT6 = amount of bill statement in April, 2005 |
| **PAY_AMT1 - PAY_AMT6** | inputs | float | amount of previous payment; PAY_AMT1 = amount paid in September, 2005; PAY_AMT2 = amount paid in August, 2005; ...; PAY_AMT6 = amount paid in April, 2005 |
| **DELINQ_NEXT**| target | int | whether a customer's next payment is delinquent (late), 1 = late; 0 = on-time |

**Test Data**
- Source of test data
- Number of rows in test data
- State any differences in columns between training and test data

