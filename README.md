# Fertility Rate Analysis with Economic Data
This is an introduction to our mini-project for Data Science & Artificial Intelligence. Our topic is economic data against fertility rate.

## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Models Used](#model-used)
- [Methodology](#methodology)
- [Conclusion](#conclusion)
- [New Insights](#new-insights)
- [Usage](#usage)


## Introduction
We took a glance on our current world population and found out that as of today, world population stands at an all-time high of over 8 billion people. This increase in world population is happening as fertility rate is higher than mortality rate. Delving deeper into research data, we found out that the most populated country is China with over 1.45 billion people and the least populated country is Niue with only 1610 people. 

It is important to note the difference between most populated and most densely populated. Some of the most densely populated countries are China and India. According to our findings, overpopulation leads to negative impacts such as ecological degradation and higher impacts of disasters and pandemics.

Next, our project also looked up on under-populated countries. Greenland only has about 0.14 people/km square and Australia has 3.44 people/km square. This also leads to certain negative effects, such as lower standard of living and poor country defence.

Since both rapid and slow population growth has their own detrimental impacts on societies, it gave us the motivation behind our current problem, "What strategies can countries implement to control their population growth?"

In our project, we'll be looking at a few datasets, namely CapitalGDP, PovertyRate, UnemploymentRate, FemalePercentage, GiniIndex and LiteracyRate against FertilityRate. Our aim is to learn from the data and come up with a response for our problem.

### Problem Definition

What strategies can countries adopt to control population growth?


### Contributors
@Shinn413 - Data Extraction, Data Preparation， Multi-Layer Perceptron

@barryyng - Problem definition, Linear Regression

@Russell-0508 - Data Preparation, Exploratory Data Analysis


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

a. Data Preparation: Divide the dataset into training and testing sets. The training set is used to train the model, while the testing set is used to evaluate its performance. Both univariate and multivariate linear regression will be considered, allowing for the analysis of single and multiple economic indicators' relationships with fertility rates.

b. Model Training: Train the Linear Regression models, both univariate and multivariate, using the training set. Fit the model to the data, learning the relationship between the economic indicators and fertility rates for each case (univariate and multivariate).

c. Model Evaluation: Evaluate the performance of the Linear Regression models, both univariate and multivariate, on the testing set using Mean Squared Error (MSE) and R-squared. This will provide insights into how well each model (univariate and multivariate) captures the relationship between the economic indicators and fertility rates.

Multilayer Perceptron (MLP):

a. Data Preparation: Just like with Linear Regression, divide the dataset into training and testing sets.

b. Model Training: Train the MLP model using the training set. The MLP model has 2 hidden layers with a specified number of neurons. We initially set the hyperparameters manually and later used GridSearchCV to find the best hyperparameters. We used PyTorch as the framework for building and training the MLP model.

c. Model Evaluation: Evaluate the performance of the MLP model on the testing set using R-squared. Compare the performance of the MLP model with the Linear Regression model to determine which one offers better predictive accuracy for the fertility rate.


## Conclusion

1. Our project has demonstrated the effectiveness of using machine learning techniques to analyze the relationship between economic indicators and fertility rates. For example, the project showed that higher literacy rates are associated with lower fertility rates so it is essential to promote education for population control.

2. Although the project does not directly address strategies for boosting population growth, it do provide valuable insights into the factors affecting fertility rates. For instance, we also found a strong positive relationship between poverty rate and fertility rate. However, it is necessary to acknowledge that higher fertility rates in impoverished areas may not be sustainable and can contribute to a cycle of poverty. In this case, strategies for boosting population growth should still focus on reducing poverty and improving the overall well-being of the population.

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
                                   
3. Open the Jupyter notebook: `Fertility Rate Analysis with Economic Data.ipynb`

4. Run the cells in the Jupyter notebook to perform the analysis and generate the results.

5. View the presentation slides in the `economic data against fertility rate.pdf` file for an overview of the project and its findings.


# References
1.https://www.worldometers.info/world-population/

2.https://www.nationsonline.org/oneworld/population-by-country.htm

3.https://www.globaldata.com/data-insights/macroeconomic/least-populated-countries-in-the-world/

4.https://ourworldindata.org/most-densely-populated-countries

5.https://www.populationmedia.org/blog/overpopulation-cause-and-effect

6.https://ourworldindata.org/most-densely-populated-countries

7.https://selfhelparchive.com/positive-and-negative-effects-of-under-population/

8.https://www.ibm.com/topics/knn#:~:text=The%20k%2Dnearest%20neighbors%20algorithm%2C%20also%20known%20as%20KNN%20or,of%20an%20individual%20data%20point.

9.https://www.d2l.ai/chapter_multilayer-perceptrons/index.html

10.https://scikit-learn.org/stable/modules/neural_networks_supervised.html
