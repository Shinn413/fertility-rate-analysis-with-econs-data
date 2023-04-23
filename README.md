# Fertility Rate Analysis with Economic Data
This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence). In this project, we predict fertility rates based on various economic indicators using machine learning techniques.

## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Models Used](#model-used)
- [Methodology](#methodology)
- [Conclusion](#conclusion)
- [New Insights](#new-insights)
- [Usage](#usage)

## Introduction

### Contributors

## Data
This project uses 7 data files, which include:

1. capital_gdp.csv
2. female percentage of total population.csv
3. fertility_rate.csv
4. Gini_index.csv   (a statistical measure of income or wealth inequality within a population rangeing from 0 to 1, where 0 indicates perfect equality and 1 represents perfect inequality)
5. Literacy_rate.csv
6. poverty_rate.csv
7. Unemployment_rate.csv

All data are extracted from the world bank https://data.worldbank.org/

## Model Used
We have utilized two machine learning models to predict the fertility rate based on the economic indicators:

1. Linear Regression Model
2. Multi-Layer Perceptron (MLP)


## Methodology

### Data Preprocessing

1. Read data from multiple CSV files, each containing information about different economic indicators (fertility rate, capital GDP, poverty rate, Gini index, literacy    rate, unemployment rate, and female percentage of the total population).

2. Drop unnecessary columns from each DataFrame such as 'Country Code', 'Indicator Name', and 'Indicator Code'.
3. Convert each DataFrame from wide format to long format using the melt() function. This involves specifying 'Country Name' as the ID variable, 'Year' as the variable    name, and the corresponding indicator name (e.g., 'FertilityRate') as the value name.
4. Merge all the DataFrames into one single DataFrame called merged_df based on the 'Country Name' and 'Year' columns. This results in a single DataFrame containing      all the economic indicators for each country and year.
5. Filter the merged_df DataFrame to include only data from 1990 onwards to improve the representativeness of the data.
6. Perform KNN imputation to fill any missing values in the merged_df DataFrame. This is done by first instantiating a KNNImputer with a specific number of neighbors      (e.g., 3). Then, the KNNImputer is fitted and used to transform the data.

### Model Development

Linear Regression:

a. Data Preparation: Divide the dataset into training and testing sets. The training set is used to train the model, while the testing set is used to evaluate its performance.

b. Model Training: Train the Linear Regression model using the training set. Fit the model to the data, learning the relationship between the economic indicators and fertility rates.

c. Model Evaluation: Evaluate the performance of the Linear Regression model on the testing set using Mean Squared Error (MSE) and R-squared.

Multilayer Perceptron (MLP):

a. Data Preparation: Just like with Linear Regression, divide the dataset into training and testing sets.

b. Model Training: Train the MLP model using the training set. The MLP model has 2 hidden layers with a specified number of neurons. We initially set the hyperparameters manually and later used GridSearchCV to find the best hyperparameters. We used PyTorch as the framework for building and training the MLP model.

c. Model Evaluation: Evaluate the performance of the MLP model on the testing set using R-squared. Compare the performance of the MLP model with the Linear Regression model to determine which one offers better predictive accuracy for the fertility rate.


## Conclusion

1. Our project has demonstrated the effectiveness of using machine learning techniques to analyze the relationship between economic indicators and fertility rates
2. Although the project does not directly address strategies for boosting population growth, it do provide valuable insights into the factors affecting fertility rates.
3. By understanding the complex relationships between these economic indicators and fertility rates with the help of data science, policymakers can tailor strategies to their specific country context.

## New Insights
1. K-Nearest Neighbors (KNN)
2. Multi-layer perceptron
3. Grid search



## Usage
To reproduce the analysis and results, follow these steps:

1. Clone this repository: `https://github.com/Shinn413/fertility-rate-analysis-with-econs-data`
2. Install the required packages: (`pip install pandas`
                                   `pip install numpy`
                                   `pip install scikit-learn`
                                   `pip install matplotlib`
                                   `pip install seaborn`
                                   `pip install torch`)
3. Open the Jupyter notebook: `SC1015.ipynb`
4. Run the cells in the Jupyter notebook to perform the analysis and generate the results.
5. View the presentation slides in the `SC1015 A128 Team 5.pdf` file for an overview of the project and its findings.

