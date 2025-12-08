# Predict Future Sales Model Card

**Basic Information**
- **Collaborators:** Garrett Harlow (garrett@acme.com), Brooke Weinberg (brooke@acme.com), Khadija Nissim (khadija@acme.com), Henry Leung (henry@acme.com), Chris Park (chris@acme.com)
- **Model Date:** November, 2025
- **Model Version:** 1.0
- **License:** Apache 2.0
- **Model Implementation Code:**

**Intended Use**
- **Intended Uses:** This model is designed to predicting sales volumes and forecast sales volumes for future months for each store and product, assisting with inventory and supply chain planning. By identifying these patterns, the model can support retail decision making and demand planning for various retail stores and product lines. 
- **Intended Users:** Data Analysts, Supply Chain Analysts, Retail Operations Managers, and E-Commerce Retailers
- **Out-of-Scope Uses:** The model should not be used to predict sales for new stores, predict individual customer purchases, or evaluate and address the financial standing of the company. 

**Training Data**
- **Source of training data:** Kaggle, https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales/overview
- **How training data was divided into training and validation data:** 97.7% test data, 2.3% validation data 
- **Number of rows in training and validation data:**
    - Rows in trained data: 1,293,041 rows 
    - Rows in validation data: 30,754 rows

**Data dictionary:** 

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
| **shop_name** | inputs | boolean | name of shop |
| **item_category_name**| target | boolean | name of item category |

**Test Data**
- **Source of test data:** https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales/overview (test.csv)
- **Number of rows in test data:** 214,200 rows
- **State any differences in columns between training and test data:** test.csv contains: 'ID', 'shop_ID', and 'item_ID' and the tagret column 'item_cnt_month' is absent from the test set 

**Model Details**
- **Columns used as input in the final model:** 'date_block_num', 'shop_id', 'item_id', 'item_category_id', 'type_code', 'city_code', 'average_item_price', 'item_cnt_month_lag_1', 'item_cnt_month_lag_2', 'item_cnt_month_lag_3', 'item_cnt_month_lag_6', 'item_cnt_month_lag_12'
- **Type of model:** Decision Tree 
- **Software used to implement the model:** Python, used in a Colab Jupyter Notebook
- **Version of the modeling software:** Python 3.14.1
- **Hyperparameters or other settings of your model:** 'objective' = 'regression', 'metric = 'rmse', 'learning_rate = .05', 'num_leaves = 64', 'feature_fraction = .8", 'bagging_fraction = .8', 'bragging_freq = 5', 'seed = 42', num_boost_round = 200-300' with early stopping on the validation set 

**Quantitative Analysis**
- Metrics used to evaluate the final model: **come back to this**
- Final values:
      - Training RMSE: 1.6974
      - Validation RMSE: 1.7416
      - Test Data:
  
  **Plots**
  - **Plots that are included in the repository:** Distribution of item_cnt_month before and after clipping, RMSE versus boosting round (LightGBM evaluation log), Feature importance plot from LightGBM (gain or split importance), Example time series for a single shop item pair (actual versus preidcted on validation month) 
  
**Ethical Considerations**

**Potential Negative Impacts**
- **Math or software problems**
  - Overfitting to historical patterns can create overly confident forecasts for rare items or new shops.
  - Data quality issues (missing data, outliers) may bias the model, especially for items with few historical sales.
  - If the feature pipeline or lag computation is incorrect, the model may artificially inflate validation performance.

- **Real-world risks**
  - **Inventory risk**: Under-prediction may lead to stockouts and lost revenue, frustrating customers and harming brand reputation. Over-prediction may cause over-stocking, markdowns, and waste.
  - **Uneven shop treatment**: If some shops systematically receive worse forecasts (e.g., because of data sparsity), they might be unfairly blamed for poor performance or receive less inventory.

**Uncertainties**
- **Math / software uncertainties**
  - Hyperparameters were tuned only on a single validation period (month 33); results might change for different time windows.
  - The model assumes stationarity – that future behavior resembles the past – which may not hold if there are major changes (new consoles, economic shocks, etc.).

- **Real-world uncertainties**
  - The data covers a specific time and region; applying the model elsewhere might lead to poor performance.
  - The model does not consider marketing campaigns, holidays, or competitor actions explicitly, which could significantly change demand.

**Unexpected findings or results**
- Some items have extremely high single-day sales that needed clipping, indicating promotions or bulk purchases.
- A small number of shops have very low or highly volatile sales; forecasts for these shops are less stable and may require manual review.
- Lag features (previous months’ sales) appear to be among the most important predictors, confirming that sales history carries strong predictive signal.

