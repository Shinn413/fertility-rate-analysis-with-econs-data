# Fertility Rate Analysis with Economic Data
This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence). In this project, we predict fertility rates based on various economic indicators using machine learning techniques.

## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Models Used](#model-used)
- [Methodology](#methodology)
- [Conclusion](#conclusion)
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


## Conclusion


## Usage
To reproduce the analysis and results, follow these steps:

1. Clone this repository: `https://github.com/Shinn413/fertility-rate-analysis-with-econs-data`
2. Install the required packages: (List any required packages and their installation commands, e.g., `pip install pandas numpy scikit-learn`)
3. Open the Jupyter notebook: `SC1015.ipynb`
4. Run the cells in the Jupyter notebook to perform the analysis and generate the results.
5. View the presentation slides in the `SC1015.ppt` file for an overview of the project and its findings.

