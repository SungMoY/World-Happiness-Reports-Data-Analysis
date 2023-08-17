# What Makes People Happy: Data Analysis of World Happiness Reports [2015-19]
By Sung Mo Yang
Tech Stack: python, jupyter notebook, numpy, matplotlib, pandas, seaborn, sklearn

## Summary
The World Happiness Report is an annual publication that assesses the well-being and happiness of people in various countries across the globe. It ranks nations based on a combination of factors, including economic indicators, social support, life expectancy, freedom to make life choices, generosity, and perceptions of corruption. This comprehensive report provides valuable insights into the factors that contribute to overall happiness and helps policymakers, researchers, and individuals understand the complex interplay between societal, economic, and personal factors that influence well-being on a global scale.<br/><br/>
This purpose of this analysis was the to determine the impact of the most significant factors contributing to the happiness of the citizens of a nation-state, as well as determine any fluctations in happiness scores/ranks over the course of half a decade.<br/><br/>
Supervised machine learning models were created, trained, and tested to determine the effectiveness of numeric, predictive models on forecasting happiness trends. By leveraging a vast dataset encompassing socio-economic variables, these models aimed to uncover intricate relationships between different parameters and overall happiness. The insights gleaned from these models could aid in formulating targeted policies, highlighting areas of improvement, and fostering a deeper understanding of the nuanced dynamics that shape well-being on a global scale.<br/><br/>
See relevant python code for further details.

## Data Preprocessing
Example of initial, unaltered data:
![DataPreprocessing1](/assets/DataPreprocessing1.png)
<br/><br/>
The World Happiness Report for 2017 requried cleaning. 'Whisker.high', 'Whisker.low', and 'Dystopia.Residual' were specifically dropped and columns were renamed to maintain consistency with the other dataset columns
![DataPreprocessing2](/assets/DataPreprocessing2.png)
<br/><br/>
The World Happiness Report for 2018 had invalid/null entries for the 'Perceptions of corruption' column (very ironic). These entries were filled with the dataset mean to maintain the average.
![DataPreprocessing3](/assets/DataPreprocessing3.png)
<br/><br/>
Resulting Dataset Columns:<br/>
![DataPreprocessing4](/assets/DataPreprocessing4.png)

## Exploratory Data Analysis
![ExploratoryDataAnalysis1](/assets/ExploratoryDataAnalysis1.png)<br/>
![ExploratoryDataAnalysis2](/assets/ExploratoryDataAnalysis2.png)<br/>
![ExploratoryDataAnalysis3](/assets/ExploratoryDataAnalysis3.png)<br/>
![ExploratoryDataAnalysis4](/assets/ExploratoryDataAnalysis4.png)<br/>
![ExploratoryDataAnalysis5](/assets/ExploratoryDataAnalysis5.png)<br/>
![ExploratoryDataAnalysis6](/assets/ExploratoryDataAnalysis6.png)

## Modeling
### Training and Test Sets
Training set: 2015-2018
Test set: 2019
The results of the predictive models were compared to the actual results of the 2019 World Happiness Report. Root Mean Square Error was used to measure accuracy and performance.

### Linear Regression
Linear regression is a type of statistical analysis used to predict the relationship between two variables. It assumes a linear relationship between the target variable and the input variables/features. It performed the best of the three models. Appear to have a linear relationship between input variables and target variables

### Random Forest Regression (Bagging)
Random forest regression is a supervised learning algorithm and bagging technique that uses an ensemble learning method for regression in machine learning. It creates a set of decision trees in parallel and then averages their predictions to obtain the final prediction. It should have been more accurate. However, since it is not as accurate when used for predictions.
It is seen as averaging previous data but happiness scores seem to be increasing with years.

### Gradient Boosting
Gradient Boosting is another ensemble learning technique that combines multiple weak predictive models, usually decision trees, to create a strong predictive model. It creates a next possible best model based off the previous. Then it adds the previous to best model in order to minimize the prediction error. Needs to be done sequentially and can’t be done in parallel.

### Results
![Results](/assets/Results.png)
<sub>Invented Score: Economy rating * 0.41 + Family rating * 0.72 + Health rating * 0.88 + Freedom rating * 0.8 + Trust rating * 0.4</sub>


### Performance and Accuracy (Root Mean Square Error)
![Performance](/assets/Performance.png)
