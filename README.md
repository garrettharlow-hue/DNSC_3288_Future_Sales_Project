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
|**ID**| ID | int | an ID that prepresents a (Shop, Item) tuple within the test set |
| **shop_id** | ID | int | unique identifier of a shop |
| **item_id** | ID | int | unique identifier of a product |
| **item_category_id** | ID | int | unique identifier of item category |
| **item_cnt_day** | demographic information | int | number of products sold. You are predicting a monthly amount of this measure |
| **item_price** | demographic information | int | current price of an item |
| **date** | demographic information | int | date in format dd/mm/yyyy |
| **date_block_num** | inputs | int | a consecutive month number, used for convenience. January 2013 is 0, February 2013 is 1,..., October 2015 is 33 |
| **item_name** | inputs | boolean | name of item |
| **shop_name** | inputs | boolean | aname of shop |
| **item_category_name**| target | boolean | name of item category |

**Test Data**
- Source of test data: https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales/overview (test.csv)
- Number of rows in test data
- State any differences in columns between training and test data

**Model Details**
- Columns used as input in the final model:
- Type of model:
- Software used to implement the model:
- Version of the modeling software:
- Hyperparameters or other settings of your model:

**Quantitative Analysis**
- Metrics used to evaluate the final model:
- Final values:
      - Training:
      - Validation:
      - Test Data:

