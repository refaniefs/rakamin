Rakamin Data Science Bootcamp Batch 20
Final Project
---------

Group 6 - dataset{'sat_set'}

Members:
- Refanie FS (Head)
- Nur Cahyanti
- Handika
- Indra Laksana
- Fajar Nurdiono
- Utlia Rahma

In this final project, we roleplay as a data science division in an e-commerce company specializing in electronic products.

--------
Dataset: E-commerce Shipment Data
--------

Dataset and Context Source: https://www.kaggle.com/datasets/prachi13/customer-analytics

The dataset used for model building contained 10999 observations of 12 variables.
The data contains the following information:

- ID: ID Number of Customers.
- Warehouse block: The Company have big Warehouse which is divided in to block such as A,B,C,D,E.
- Mode of shipment:The Company Ships the products in multiple way such as Ship, Flight and Road.
- Customer care calls: The number of calls made from enquiry for enquiry of the shipment.
- Customer rating: The company has rated from every customer. 1 is the lowest (Worst), 5 is the highest (Best).
- Cost of the product: Cost of the Product in US Dollars.
- Prior purchases: The Number of Prior Purchase.
- Product importance: The company has categorized the product in the various parameter such as low, medium, high.
- Gender: Male and Female.
- Discount offered: Discount offered on that specific product.
- Weight in gms: It is the weight in grams.
- Reached on time: It is the target variable, where 1 Indicates that the product has NOT reached on time and 0 indicates it has reached on time.

--------
Stage 1 Overview: Exploratory Data Analysis
--------

We did exploratory data analysis (EDA) on our data, with workflow as described below:
1. We described the data using df.info() and df.describe() functions,
2. We did univariate analysis of each columns,
3. We did multivariate analysis between feature columns and target column, and
4. We explained the business insights we've gathered by grouping and aggregating columns we deemed interesting and valuable.

Stage 1 conclusions:
- There are no missing values and no inconsistent values.
- There are outliers in a few columns.
- There are many columns with non-normal distributions, a few are skewed and a few with bimodal distributions.
- The target column is slightly imbalanced with 60:40 distribution, where ~60% is late shipment and ~40% on-time shipment. 

--------
Stage 2 Overview: Data Preprocessing
--------

Data preprocessing can be divided into two parts, the first part is data cleansing and the second is feature engineering.

Our workflow in data cleansing can be described like this:
1. We transform the non-normal columns, each with quantile and logarithmic transformations,
2. We remove the outliers from Discount Offered column,
3. We encode the features using label encoding for columns with exactly 2 distinct features and ordinal values, also onehot encoding for columns with nominal values,
4. We drop irrelevant columns and columns that will cause data leakage, i.e. ID, Customer Care Calls, and Customer Rating, and
5. We add 3 more columns, such as the ratio of Cost of the Product and Weight in gms, Cost of the Product after Discount, and Weight Level.

--------
Stage 3 Overview: Modelling and Evaluation
--------

In this stage, we make a model with various machine learning algorithms and evaluate it with metrics of our considerations.
After this, we rank the features from the most to the least important.

The algorithms we use with its default hyperparameter:
1. Logistic Regression
2. K-Nearest Neighbor
3. Decision Tree
4. Random Forest
5. Gradient Boosting
6. Gaussian Naive-Bayes
7. AdaBoost
8. XGBoost

After making the models, we consider those metrics as important (with descending order from most important to least important):
1. Small difference between AUC-train and AUC-test (to determine whether the model is overfitting or not),
2. AUC-train score below 1.00,
3. Recall of test data, and

We tune all of the algorithms above except AdaBoost with various hyperparameter and find the best parameters with RandomizedSearchCV. In the end, we make a feature importance ranking. 

Stage 3 conclusions:
- We choose a model with Logistic Regression since the model has the highest metric values of all the models we've tried so far,
- We decide to drop the least important columns, and
- According to the ranking, we see that the discount has the highest score, which means the higher the discount, the later the product will arrive.

--------
Overall Conclusions and Business Recommendations
--------

More to come! :)

Thank you!
