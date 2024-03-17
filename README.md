# Capstone-Project-Final-Report
Capstone Project Final Report and Exploratory Data Analys for UC Berkeley Professional Certificate of ML and AI course, August 2023 to March 2024

## What are the key characteristics of tennis players who win, especially in very close matches that last for five sets? How accurately can professional tennis match outcomes be predicted using match statistics?
Fredrik Pettersson

# Executive Summary
Match statistics from 30,000 professional single men's ATP tennis matches played between 2010 and 2022 were analyzed to understand what the key predictors of winning players are, particularly during close five set matches.

It was found that the strongest predictors which differentiate winners from losers include 1) Number of breakpoints lost while serving as a percentage of total serve points (on average 2.8% vs 3.7% for winners and losers, respectively), and 2) Number of first serves that resulted in a winning point as a percentage of total serve points (on average 46% vs 43% for winners and losers, respectively), based on a total of 1105 five-set matches played between 2010 and 2022.

In addition, six different machine learning models, Logistic Regression, K-Nearest Neighbor (KNN), Decision Trees, Support Vector Machines (SVM), Random Forest, and Neural Networks were trained and evaluated on the full dataset containing 35 different kinds of match statistics as well as a reduced dataset of 16 features that only contains information that is available before the match is played.

It was found that the Decision Tree Classifier generally performed very well with a prediction accuracy score of 0.92 (using validation data) on the full set of features against the baseline model of 0.66, which simply assumes that the highest ranked player wins. Also, by training a model specifically for a certain player, such as Novak Djokovic, it was found that prediction performance can be significantly enhanced to 99% accuracy with the Decision Tree model, compared to 84% with the baseline model, for the full dataset involving all match statistics. 

However, predicting match outcome on the reduced dataset, that only contains information available before the match is played, is significanlty more difficult. The Random Forest model performed the best at 89% accuracy on a model trained specifically on the matches played by Novak Djokovic compared to the baseline model performance of 84%. Also, the neural network and SVM models performed relatively well at 88% and 87% accuracy, respectively. 

# Rationale
I expect to extract insights on what features and aspects of the game contribute the most to winning tennis matches to inform how we practice and prepare for matches.

My research question is important as tennis is a very large sport that is played by not only professionals, but also millions of amateurs worldwide who spend billions of dollars trying to improve their games and win local competitions.

# Research Question
The research question is to understand what the key characteristics and predictors are of tennis players who win, especially in very close matches that last for five sets. Also, I would like to explore whether it is possible to create a machine learning model that is better at predicting the winner than simply using the official ATP ranking, which is used as the baseline performance measure.

# Data Sources
The data used for this study is the the Kaggle ATP Matches dataset that contains details about all the ATP tennis matches played since 1968 with detailed match statistics available for matches since 1991 ATP matches (available at https://www.kaggle.com/datasets/sijovm/atpdata/data).

# Methodology
The methods I use for answering my questions include common data science practices and visualization techniques using Python programming and Panda dataframe manipulations as well as common machine learning models such as Logistic Regression, K-Nearest Neighbors, Decision Tree Classifiers, Support Vector Machines, Random Forests, Neural Networks, and the GridSearchCV function to optimize the choice of hypermodel parameters to get the best prediction performance.

The full feature data set with 35 numerical features and the reduced data set with 15 numerical features along with the target feature 'winner' were developed from the original ATP match dataset:



![feature data sets](https://github.com/fredrik-pettersson/Capstone-Project-Final-Report/assets/146313002/acdf410c-4daf-41a8-8c18-5d74451d161d)



# Results
I found that the strongest predictors that differentiate winners from losers include 1) Number of breakpoints lost while serving as a percentage of total serve points (on average 2.8% vs 3.7% for winners and losers, respectively), and 2) Number of first serves that resulted in a winning point as a percentage of total serve points (on average 46% vs 43% for winners and losers, respectively), based on a total of 1105 five-set matches played between 2010 and 2022 (see charts below with winning player on x-axis and losing player on y-axis): 
![bpLostPerct](https://github.com/fredrik-pettersson/Capstone-Project-Final-Report/assets/146313002/d413ee9b-c65a-4b39-ae2a-f9ef6300d003)

![1stWonPerct](https://github.com/fredrik-pettersson/Capstone-Project-Final-Report/assets/146313002/790733db-8363-4a8f-aef5-6214cd8ca8ed)



Other characteristics such as age of the players and duration of the matches did not seem to have any significant impact on the match outcomes (see charts below):

![winner age vs loser age](https://github.com/fredrik-pettersson/Capstone-Project-Final-Report/assets/146313002/ad1038ca-7390-4c2d-8350-15153ad8504e)

![winner age vs minutes2](https://github.com/fredrik-pettersson/Capstone-Project-Final-Report/assets/146313002/3d24254b-d2bb-4a8b-b922-f18dece7bf9b)

![winner age vs minutes](https://github.com/fredrik-pettersson/Capstone-Project-Final-Report/assets/146313002/4062319a-17a3-47d8-a264-6d4acb20c30e)


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
