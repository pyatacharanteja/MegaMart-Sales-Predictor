Big Mart Sales Predictor (XGBoost)

A regression model that forecasts item-level sales for Big Mart outlets using XGBoost.

Dataset

Big Mart sales data: 8,523 rows and 12 columns covering item attributes (weight, fat content, visibility, type, MRP) and outlet attributes (identifier, size, location type, outlet type, establishment year). The target is Item_Outlet_Sales.

Approach
Cleaning: filled missing Item_Weight with the mean and missing Outlet_Size with the most common size for each outlet type. Standardised inconsistent Item_Fat_Content labels (LF, low fat, reg).
EDA: distributions of weight, visibility, MRP and sales, plus counts by fat content, item type, outlet size and establishment year.
Encoding: label-encoded categorical columns.
Modelling: 80/20 train/test split (random_state=2) and an XGBRegressor, evaluated with R².
Results
Set	R²
Training	0.79
Test	0.74

The small gap between training and test R² suggests limited overfitting on this split.

Limitations and next steps
Evaluated on a single random split with R² only; cross-validation and error metrics (MAE, RMSE) would give a fuller picture.
Label encoding is applied to identifier columns; target or one-hot encoding may work better.
No hyperparameter tuning yet.
Feature engineering (for example outlet age from establishment year) is a planned improvement.
Files
Mega_Mart_Sales_Prediction.ipynb: full notebook
Train.csv: dataset
