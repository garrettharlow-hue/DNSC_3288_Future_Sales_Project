# Predict Future Sales

**Basic Information**
- Collaborators: Garrett (garrett@acme.com), Brooke (brooke@acme.com), Khadija (khadija@acme.com), Henry (henry@acme.com), Chris (chris@acme.com)
- Model Date: November, 2025
- Model Version: 1.0
- License: Apache 2.0
- Model Implementation Code:

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
- Number of rows in test data: 214,200 rows
- State any differences in columns between training and test data: -test.csv contains: 'ID', 'shop_ID', and 'item_ID'
- The tagret column 'item_cnt_month' is absent from the test set 

**Model Details**
- Columns used as input in the final model: 'date_block_num', 'shop_id', 'item_id', 'item_category_id', 'type_code', 'city_code', 'average_item_price', 'item_cnt_month_lag_1', 'item_cnt_month_lag_2', 'item_cnt_month_lag_3', 'item_cnt_month_lag_6', 'item_cnt_month_lag_12'
- Type of model: gradient boosted decision tree using lightGBM in regression mode 
- Software used to implement the model: Python
- Colab
- The libraries we used in our code were Pandas for data wrangling, Numpy for nuemric operations, LightGBM for the gradient boosting model, sikitlearn for evaluation metrics and utilities, and matplotlib for our visualizations
- Version of the modeling software: Python 3.14.1
- Hyperparameters or other settings of your model:
- 'objective' = 'regression', 'metric = 'rmse', 'learning_rate = .05', 'num_leaves = 64', 'feature_fraction = .8", 'bagging_fraction = .8', 'bragging_freq = 5', 'seed = 42', num_boost_round = 200-300' with early stopping on the validation set 

**Quantitative Analysis**
- Metrics used to evaluate the final model: **come back to this**
- Final values:
      - Training: 
      - Validation:
      - Test Data:
  
  **Plots**
  - Plots that are included in the repository:
  - Distribution of item_cnt_month before and after clipping
  - RMSE versus boosting round (LightGBM evaluation log)
  - Feature importance plot from LightGBM (gain or split importance)
  - Example time series for a single shop item pair (actual versus preidcted on validation month) 
  
**Ethical Considerations**
- Describe potential ethical impacts of using your model
-     Math or software problems: 
-     Real-world risks 

