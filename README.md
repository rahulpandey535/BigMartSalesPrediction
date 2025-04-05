# BigMartSalesPrediction

🛒 Big Mart Sales Prediction

Predicting sales for retail products using machine learning to assist Big Mart in managing inventory, stocking, and business decisions.
📌 Problem Statement

Big Mart, a retail chain, aims to forecast the sales of products at various stores using historical data. By understanding sales patterns, the company can:
Optimize inventory planning
Improve resource allocation
Enhance profit margins
📊 Dataset Description

The dataset consists of 2013 sales data for products across 10 stores of Big Mart.
📁 Files:
Train.csv – Contains features and target sales.
Test.csv – Contains features only (used for prediction).
🧾 Key Features:
Column	Description
Item_Identifier	Unique product ID
Item_Weight	Weight of the product
Item_Fat_Content	Whether the product is low fat or regular
Item_Visibility	Percentage of total display area of all products
Item_Type	Category of product
Item_MRP	Maximum Retail Price of the product
Outlet_Identifier	Unique store ID
Outlet_Establishment_Year	Year store was established
Outlet_Size	Size of the store
Outlet_Location_Type	City tier
Outlet_Type	Type of outlet
Item_Outlet_Sales	(Target) Sales of the product in a particular store
🧪 Exploratory Data Analysis (EDA)

Checked for missing values and data types
Visualized product types, outlet types, and sales distribution
Treated outliers and performed feature engineering (e.g., combining similar categories)
🛠️ Data Preprocessing

Imputed missing values (Item_Weight, Outlet_Size)
Converted categorical features using:
Label Encoding
One-Hot Encoding (where applicable)
Normalized skewed features
Created new features like Years_Operation
🤖 Model Training

📦 Algorithm Used: XGBoost Regressor
✅ Rationale: Fast, handles missing data, supports regularization, works well with tabular data
🧠 Trained on X_train and Y_train after preprocessing
from xgboost import XGBRegressor

regressor = XGBRegressor()
regressor.fit(X_train, Y_train)
📈 Model Evaluation

Used Root Mean Squared Error (RMSE) as the metric
Performed cross-validation to avoid overfitting
Achieved competitive accuracy on validation data
📤 Predictions

Predictions on the test set (Test.csv) were generated and saved for submission.
predictions = regressor.predict(X_test)
submission = pd.DataFrame({
    "Item_Identifier": test_data["Item_Identifier"],
    "Outlet_Identifier": test_data["Outlet_Identifier"],
    "Item_Outlet_Sales": predictions
})
submission.to_csv("submission.csv", index=False)
📌 Conclusion

Accurate sales prediction can significantly enhance Big Mart's supply chain and marketing strategies.
Future improvements:
Hyperparameter tuning
Try advanced models like CatBoost, LightGBM
Integrate external data like holiday calendars, promotions
📚 Libraries Used

Python 🐍
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn
XGBoost
🚀 Author

👤 Rahul Pandey
🎓 Computer Science Student | Aspiring Data Scientist

