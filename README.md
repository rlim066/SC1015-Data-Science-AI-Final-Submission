# SC1015 Data Science Mini Project

## About 
This is the mini project for SC1015. Our team's objective is to create a model that can best predict the IMDb scores of movies.


## Contributors
-Timothy Lim: Data Extraction & Preparation, Exploratory Data Analysis, Slides

-Raymond Lim: Data Preparation, Categorical Linear Regression, Slides

-Duy Linh: Exploratory Data Analysis, Numerical Linear Regression, Random Forest, Slides

## Original Data Sets
Movies on Streaming Platforms 2021: https://www.kaggle.com/code/ruchi798/movies-and-tv-shows-eda/data?select=MoviesOnStreamingPlatforms_updated.csv 

Movies on Streaming Platforms 2020 https://www.kaggle.com/code/armintalic/quality-and-quantity-of-streaming-services-content/data?select=MoviesOnStreamingPlatforms_updated.csv

## Problem Definition
-Are we able to predict the IMDb Score of Movies based on their metrics?

-Which metrics are the best for accurate predictions?

-How will different modelling strategies affect our predictions?

## Models Used
1. Numeric Linear Regression
2. Multivariate Linear Regression
3. Random Forest Regression

## ipynb notebook
### 1. Data Extraction
This notebook contains code that we used to extract the data from the csv files, as well as cleaning up the data. Additionally, we used excel formulas to clean the dataset. Firstly, we combined the two data sets we had into one dataset, and removed all duplicate rows. We then changed the data type of IMDb and Rotten Tomatoes scores to float64 datatype using excel formulas such as =VALUE(LEFT(CELL_NAME,LEN(CELL_NAME)-INT)). Next, we added a new column, Availalility, which counts the number of streaming platforms a movie is on. We only kept the first Country, Genre and Language, to ease the EDA process. Lastly, we removed all columns we deemed unnecessary and dropped all rows with N.A values, and saved the dataset into a new csv file.


### 2. Exploratory Data Analysis
In this notebook, we first checked the dataset for any anomalies. In the case of the variable Runtime, there were many data points outside the box and whiskers plot, and we removed them from the dataset. We then did EDA on the numerical variables and categorical variables. For the numerical variables, we displayed  the spreads of all the variables, as well as the Correlation Matrix. For categorical variables, we found that for some variables, there were too many categories,which made it impossible to display. Hence, we decided to keep the top 10 categories of each variable that had the most movies in them. 

### 3. Numeric Linear Regression
In this notebook, we find the best numeric variable, Rotten Tomatoes score, Runtime and Age of Movie to predict the IMDb scores. Univariate regression was performed on all three variables. The best variable would have the highest R^2 value and the lowest Mean Squared Error (MSE) from its test set. We came to the conclusion that the Rotten Tomatoes score was the best variable to predict IMDb scores.

### 4. Categorical Linear Regression
In this notebook, we use dummy coding to change our categorical variables into numeric variables, in order to make use of our Categorical Data into forming a Multivariate Regression Model. We used the function get_dummies to create dummy variables. We then split the dataframe into a test and train set, and found that it had a better goodness of fit compared to numerical linear regression. 

After creating the Multivariate Regression Model, we used it to predic the IMDb scores of a few specific movies - *The Matrix, Back to the Future and Spider-Man: Into the Spider-Verse*. The average error of the predictions is was 14% for these 3 movies.


### 5. Random Forest Regression

## Conclusion
1. Rotten Tomatoes score is the best variable to predict IMDb score as it had the highest correlation and the best Goodness of Fit model out of all three numerical variables.
2. We found that by using dummy coding and a Multivariate Regression Model,  we were able to improve our prediction over just using numerical variables only.
3. Random Forest was able find the most important variable in predicting IMDb score
4. Random Forest Regression was a worser prediction model compared to Multivariate Regression, when it comes to predicitng IMDb scores.


## Lessons Learnt
1. Combining Datasets and cleaning them using python and excel formulas.
2. Learnt how to use Dummy Coding to do linear regression using categorical variables.
3. We learnt how to predict variabkles using Random Forest Regression Model.
4. Collaborating using GitHub.


## References
1. https://medium.com/analytics-vidhya/implementing-linear-regression-using-sklearn-76264a3c073c
2. https://www.statisticssolutions.com/dummy-coding-the-how-and-why/
3. https://www.moresteam.com/whitepapers/download/dummy-variables.pdf
4. https://cnvrg.io/random-forest-regression/
