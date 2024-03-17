# Capstone-Project-Final-Report
Final Report and Exploratory Data Analyss for UC Berkeley Professional Certificate of ML and AI course August 2023 to March 2024

## What are the key characteristics of tennis players who win, especially in very close matches that last for five sets?
Fredrik Pettersson

# Executive Summary
Match statistics from 30,000 professional single men's ATP tennis matches played between 2010 and 2022 were analyzed to understand what the key predictors of winning players are, particularly during close five set matches.

It was found that the strongest predictors that differentiate winners from losers include 1) Number of breakpoints lost while serving as a percentage of total serve points (on average 2.8% vs 3.7% for winners and losers, respectively), and 2) Number of first serves that resulted in a winning point as a percentage of total serve points (on average 46% vs 43% for winners and losers, respectively), based on a total of 1105 five-set matches played between 2010 and 2022.

In addition, four different machine learning models, Logistic Regression, K-Nearest Neighbors (KNN), Decision Trees, and Support Vector Machines (SVM), were trained and evaluated on the full dataset containing 35 different kinds of match statistics as well as a reduced dataset that only contains those features that are available before the match is played.

It was found that the Decision Tree Classifier performed by far the best with a prediction accuracy score of 0.92 on the full dataset.

# Rationale
I expect to extract insights on what features and aspects of the game contribute the most to winning tennis matches to inform how we practice and prepare for matches.

My research question is important as tennis is a very large sport that is played by not only professionals, but also millions of amateurs worldwide who spend billions of dollars trying to improve their games and win local competitions.

# Research Question
The research question is to understand what the key characteristics and predictors are of tennis players who win, especially in very close matches that last for five sets. Also, I would like to explore whether it is possible to create a machine learning model that is better at predicting the winner than simply using the official ATP ranking, which is the baseline performance measure.

# Data Sources
The data used for this study is the the Kaggle ATP Matches dataset that contains details about all the ATP tennis matches played since 1968 with detailed match statistics available for matches since 1991 ATP matches (available at https://www.kaggle.com/datasets/sijovm/atpdata/data).

# Methodology
The methods I use for answering my questions include common data science practices and visualization techniques using Python programming and Panda dataframe manipulations as well as common machine learning models such as Logistic Regression, K-Nearest Neighbors, Decision Tree Classifiers, Support Vector Machines, and the GridSearchCV function to optimize the choice of hypermodel parameters to get the best prediction performance.

The following 35 numerical features and the target feature 'winner' were developed from the original ATP match dataset:

image

# Results
I found that the strongest predictors that differentiate winners from losers include 1) Number of breakpoints lost while serving as a percentage of total serve points (on average 2.8% vs 3.7% for winners and losers, respectively), and 2) Number of first serves that resulted in a winning point as a percentage of total serve points (on average 46% vs 43% for winners and losers, respectively), based on a total of 1105 five-set matches played between 2010 and 2022 (see charts below with winning player on x-axis and losing player on y-axis): bpLostPerct 1stWonPerct

Other characteristics such as age of the players and duration of the matches did not seem to have any significant impact on the match outcomes (see charts below):

winner age vs loser age winner age vs minutes2 winner age vs minutes

In addition, four different machine learning models, Logistic Regression, K-Nearest Neighbors (KNN), Decision Trees, and Support Vector Machines (SVM), were trained and evaluated on the full dataset containing 35 different kinds of match statistics as well as a reduced dataset that only contains those features that are available before the match is played. It was found that the Decision Tree Classifier performed by far the best with a prediction accuracy score of 0.92 on the full dataset with 35 columns of match statistics and player information (table below):

image

To investigate the performance of the above prediction models on individual players, I prepared a dataset with 747 matches that Novak Djokovic played between the years 2010 and 2022. Similarly to the earlier results, the Decision Tree model again performed the best by far with an accuracy score of 0.99, while the other models were not even able to meet the baseline performance measure of 0.84, which is achieved by simply predicting that the player with the highest ranking points will win the match (table below):

image

The prediction performance results of the above models on the reduced dataset that only contains match data that is known BEFORE the match were not able to exceed the baseline performance. In this case, the Logistic Regression, Decision Tree, and SVM models performed about the same at around 0.66 even after hypermodel parameter optimization using GridSearchCV (see table below):

image

Next Steps
I would like to further explore why the Decision Tree model had such an outstanding prediction performance among the four models that I evaluated:

image

Contact and Further Information
Fredrik Pettersson, email: fc.pettersson@gmail.com
