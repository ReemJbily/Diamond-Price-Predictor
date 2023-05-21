# Diamond-Price-Predictor
### This repository is the solution to the diamond price predictor competition on Kaggle.

### It is part of my training with SHAI for AI.

### The data set is available here and it is divided into train and test sets.

### The project went through different stages of machine learning life cycle.

# Project life cycle:
### 1-The big picture:
#### After picking up some information on factors that affect diamond price, we found five factors that affect the price directly:
#### Colour, Clarity, Carat, Cut and shape of the diamond.
### 2-Data explorination:
#### In this project we explored the train data set using numpy and panadas libraries.
#### We found that:
#### -Data set has three categorical columns which are ‘cut’, ‘color’ and ‘clarity columns and they are all ordered.
#### -The x, y and z columns have the min value zero which indicates fault values, and they have their max value differs from the 75% value which indicates outliers.
#### -There is a strong positive relation between carat, x, y and z of the diamond and its price.
#### -There are 5 zero values in x column, 4 zero values in x column and 17 zero values in z column.
### 3-Data Visualization:
#### For visualizing data, we used boxplots to detect outliers and their values, scatter plot to investigate the relation between variables and heatmap for features’ correlation.
#### Some insights we got after visualizing the train data using pandas, seaborn and matplotlib:
#### •	Outlier values in x, y and z columns are less than 30.
#### •	Outlier values in depth column are in range ]45, 75[
#### •	Outlier values in table column are in range ]40, 80[
### 4-Preprocessing:
#### In order to make data more efficient for training the , we:
#### 	Removed zero values from z, y and z columns.
#### 	Removed outliers from x, y, z, depth and table columns.
#### 	Column transformation:
#### For numerical columns we used:
#### •	Simple Imputer(strategy=median) so any missed nan value will be replaced by the median value of its column.
#### •	CombinedAttributeAdder: to add the volume column which is x*y*z values.
#### •	StandardScaler: to scale the data for better training.
#### For exponentially distributed data we used:
#### •	FunctionTransformer: that applies log transform.
#### For categorical columns we used:
#### •	OrdenalEncoder: to convert categorical values in the ‘cut’, ’color’ and ‘clarity’ columns into numerical values which will take values like 1, 2, 3 …
#### •	StandardScaler.
### 5-Select and train the model:
#### For this project, we selected five regression models: Linear Regression, Lasso Regression, Decision Tree, Random Forest, XGBoost Regressor and Voting Regressor.
### 6-Fine Tune the model:
#### For this stage we used random search on random forest and got that n_estimators =1000 is the best.
### 7-Evaluating models using cross validation.
### 8-Saving the results:
#### In this step predictions on the test set were performed using the chosen model, then saved the result as a csv file.
# Results:
#### after comparing the different models using the RMSE, we found that the best result was achieved using voting regressor with random #### forest (n_estimators=1000, random_state=42) and XGBoost (n_estimators=300, lr= 0.1) with just adding volume feature.

