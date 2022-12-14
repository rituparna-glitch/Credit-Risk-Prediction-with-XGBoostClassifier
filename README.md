# Credit-Risk-Prediction-with-XGBoostClassifier
- Merged the two datasets into a single one by inner joining them with primary key value applicant id. 
- Counted the null value and null value percentage for each column.
- Dropped the column with more than 80% missing values
  - For columns with more than 30% missing values performed the chi square test to see how relevant those columns are for the target variable. The test fail to reject the null hypothesis that the columns are independent. Hence we dropped the columns. 
  - Imputed missing values for rest of the columns. 
- Calculated the outliers for continuous variables and capped them. 
- Measured the Correlation coefficient of the numeric variables.
- Measured VIF for the variables for further feature selection. 
  - Dropped the columns until the VIF was within acceptable range ( < 10 )
- Removed redundant features (ids) 
- Label encoded the categorical variables
- To handle the imbalanced dataset SMOTE was used in the Model training pipeline. 
- Recall value was given more priority for reducing the False Negatives as per the business constraints. 
- Fitted 3 ML models:
  - Decision Tree Classifier
  - Random Forest Classifier
  - XGBoost Classifier
- Used RandomizedSearchCV for hyper parameter tuning.
- Recall score of XGBoost model outperformed the other two. 
