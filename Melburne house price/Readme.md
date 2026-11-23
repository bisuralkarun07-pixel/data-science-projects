Melbourne Housing Price Prediction
Project Overview

House prices depend on several factors, including location, number of rooms, property size, distance from the city center, and property type.

The objective of this project is to analyze the Melbourne housing dataset and develop machine learning regression models to predict house prices based on different property features.

Two regression algorithms are implemented and compared:

Linear Regression
Random Forest Regressor

The performance of both models is evaluated using R² Score and Mean Absolute Error (MAE).

Dataset

The project uses the Melbourne Housing Dataset, which contains information about residential properties in Melbourne, Australia.

Dataset Information
Initial records: 34,857
Initial features: 22
Target variable: Price
Problem type: Supervised Machine Learning (Regression)
Important Features
Feature	Description
Suburb	Location of the property
Rooms	Number of rooms
Type	Type of property
Method	Method of sale
SellerG	Real estate agent
Date	Date of property sale
Distance	Distance from the city center
Postcode	Property postcode
Bedroom	Number of bedrooms
Bathroom	Number of bathrooms
Car	Number of car spaces
Landsize	Land size of the property
CouncilArea	Local government area
Latitude	Geographic latitude
Longtitude	Geographic longitude
Regionname	Metropolitan region
Propertycount	Number of properties in the suburb
ParkingArea	Type of parking area
Price	Property selling price
Technologies and Libraries

The project is implemented using Python and the following libraries:

Pandas – Data manipulation and analysis
NumPy – Numerical operations
Matplotlib – Data visualization
Seaborn – Statistical data visualization
Scikit-learn – Machine learning and model evaluation
Project Workflow
1. Data Loading and Exploration
Loaded the dataset using Pandas.
Examined the first five records using head().
Checked the dataset dimensions using shape.
Inspected data types and non-null values using info().
Used describe() to understand numerical feature distributions.
Identified missing values in the dataset.
2. Data Cleaning and Preprocessing

Missing values were identified using isnull().sum() and their percentages were calculated.

The following preprocessing steps were performed:

Removed the BuildingArea column because approximately 60.52% of its values were missing.
Removed the YearBuilt column because approximately 55.39% of its values were missing.
Removed the Address column because it contains highly unique values.
Removed records with missing target values (Price).
Used median imputation for numerical features.
Used most frequent imputation for categorical features.
Applied One-Hot Encoding to convert categorical variables into numerical representations.
3. Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand the distribution of housing prices and the relationships between different property features.

Numerical Analysis:

Used histograms to examine numerical feature distributions.
Used scatter plots to understand relationships between numerical variables and house prices.
Used box plots to identify potential outliers.
Created scatter plots with property type and region to explore their relationship with housing prices.

Categorical Analysis:

Examined the number of unique categories in categorical features.
Used count plots to visualize the distribution of categorical variables.
Analyzed features such as property type, sale method, seller, council area, region, and parking area.

Missing Value Analysis:

Calculated missing value counts and percentages.
Visualized missing values using a heatmap.
4. Feature Selection

The following columns were removed:

Address – Highly unique and less suitable for direct categorical encoding.
BuildingArea – Contains approximately 60.52% missing values.
YearBuilt – Contains approximately 55.39% missing values.

The target variable was:

Price

All remaining features were used as independent variables.

5. Train-Test Split

The dataset was divided into training and testing sets using Scikit-learn's train_test_split().

Training data: 80%
Testing data: 20%
Random state: 10
6. Data Preprocessing Pipeline

A preprocessing pipeline was developed using Scikit-learn.

Numerical Features:

Missing values were handled using SimpleImputer(strategy='median').

Categorical Features:

Missing values were handled using SimpleImputer(strategy='most_frequent').
Categorical variables were transformed using OneHotEncoder(handle_unknown='ignore').

A ColumnTransformer was used to combine numerical and categorical preprocessing.

Machine Learning Models
Model 1: Linear Regression

Linear Regression was implemented as the baseline regression model.

It attempts to establish a linear relationship between property features and house prices.

Model:

Algorithm: Linear Regression
Preprocessing: Numerical imputation and categorical encoding

Evaluation Results:

R² Score: 0.6909
Mean Absolute Error: 232,340.54
Model 2: Random Forest Regressor

Random Forest Regressor was implemented to capture more complex relationships between property features and house prices.

It combines multiple decision trees and averages their predictions to produce the final result.

Hyperparameters:

Number of estimators: 150
Maximum depth: 15
Minimum samples split: 5
Random state: 10

Evaluation Results:

R² Score: 0.7941
Mean Absolute Error: 171,525.40
Model Evaluation

The models were evaluated using two regression metrics.

1. R² Score (Coefficient of Determination)

R² measures how much of the variation in the target variable is explained by the model.

A higher R² score indicates better explanatory performance.

2. Mean Absolute Error (MAE)

MAE measures the average absolute difference between actual and predicted house prices.

A lower MAE indicates better prediction accuracy.

Model Comparison

The following table compares the performance of both regression models.

Evaluation Metric	Linear Regression	Random Forest
R² Score	0.6909	0.7941
MAE	232,340.54	171,525.40
Model Performance Visualization

The comparison shows that Random Forest performs better than Linear Regression on both evaluation metrics.

Random Forest achieved a higher R² score of approximately 79.41%.
Random Forest achieved a lower MAE of approximately 171,525.
Linear Regression achieved an R² score of approximately 69.10%.
Linear Regression had a higher MAE of approximately 232,341.
Conclusion

In this project, two machine learning regression algorithms were implemented to predict Melbourne housing prices.

Based on the evaluation results, Random Forest Regressor performed better than Linear Regression.

Random Forest achieved:

Higher R² Score: 0.7941
Lower MAE: 171,525.40

This indicates that Random Forest captures the relationships between housing features and property prices more effectively than the Linear Regression model in this experiment.

Therefore, Random Forest Regressor is the better-performing model among the two models tested.

Future Improvements

The model performance could potentially be improved through:

Hyperparameter tuning using GridSearchCV or RandomizedSearchCV.
Feature engineering to create more informative features.
Outlier detection and treatment.
Log transformation of highly skewed numerical features and the target variable.
More advanced regression algorithms such as Gradient Boosting, XGBoost, and HistGradientBoosting.
Cross-validation for more reliable model evaluation.
Further analysis of geographical features such as latitude, longitude, and suburb.
Project Structure
text
Melbourne-Housing-Price-Prediction/
│
├── Melbourne_housing.csv
├── Melbourne_Housing_Prediction.ipynb
└── README.md

How to Run the Project

Step 1: Clone or download this repository.

Step 2: Install the required libraries.

bash
pip install pandas numpy matplotlib seaborn scikit-learn


Step 3: Keep the dataset in the project directory.

Step 4: Open Jupyter Notebook.

bash
jupyter notebook


Step 5: Open Melbourne_Housing_Prediction.ipynb and execute the cells sequentially.

Project Goal: To develop a machine learning model that predicts Melbourne property prices using property characteristics and location-related information.
