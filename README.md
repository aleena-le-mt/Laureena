# Board Games
## Segment 1 - Getting Started
### Project Overview
We have recently found some data on board games and decided to work on this topic because board game data is interesting and fun to work on with all the different ways in which people win and think about these games. Something that is different in board game data compared to other online games is how raw it can be. With online games, we only end up with data created through technology itself. However, with board games, we can ensure that the data that we collect are all from real life people playing these games without any form of technology being apart of it.

### Purpose
The purpose of this project is to analyze the various data points presented in the board game dataset and see if we can find any correlations between those data points on either the games' ratings or the games' complexity to create a model that could predict what makes a good game.

### Resources
- Raw Data: https://www.kaggle.com/andrewmvd/board-games/version/2
- Data Source: BoardGameGeek.com
- Software: Excel 365, Python 3.6.1

### Description & Links of Datasource
The website "BoardGameGeek.com" allows users to rank board games on a scale of 1-10, and the site presents an average rating based on those individual ratings. This data is a collection of all ranked games in the BGG database.

### Questions To Answer
We hope to be able to answer questions related to game ratings and complexity such as...
- How complex the games are according to people's ratings of the games?
- What are the games' maximum amount of players?
- What are the games' average play time?
- What are the games' average complexity?
- Can we reasonably and accurately predict the average game rating?

### Challenge Summary
Things we had trouble with:
- Finding a dataset that is reliable and interesting to work on. 
- Getting our data into pgAdmin because when we tried running the data in Jupyter Notebook, there was an error saying "psycopg2" does not exist. We were able to resolve this by putting in "pip install psycopg2-binary" into the pythondata terminal that we used to open Jupyter Notebook. 
- The first learning model produced predictions that were not within a normal range of the other predictions or the dataset "Rating Averages". The describe function used on features showed "Years Published" had values in the negative such as -3500. All data with "Years Published" before 1800 was removed before training and testing the model. The new dataframe produced a new scatter plot without extreme outliers.

### Communication Protocols
We reach out to each other on Slack and decided on a day and time in which we all agreed to meet up on each week from now on, 3PM on Fridays. Whenever a question arises, we would ask eachother and if we all end up not knowing the answer, then we ask our captain, Savannah.

## Segment 2 - Refining Model
### Project Overview
Initially Laura took the dataframe trying to form a model with four files:
- mlr_after_1800_wtih_db.ipynb
- mlr_getdummies_predict_rating.ipynb
- mlr_predict_average_rating_with_db.ipynb
- mlr_predict_complexity_wtih_db.ipynb

The accuracy scores of the these files were not high enough and so she ended up making another file with a model that we will be talking about for this segment:
- Multiple_linear_regression_model.ipynb

### Description of Model
This is a scatterplot of the correlation between actual rating averages from our board game data and the predicted rating averages. The way that this model works is that it compares actual and predicted rating averages. The reason why this model was initially chosen was because its accuracy is the best out of all the others that were done. This model has an accuracy of 70% and the statistics included in analysis is mainly the rating averages from our data. The reason why our statistic is average ratings is because it is one of the only statistical data that seems best to analyze so far together with complexity.

<img width="442" alt="Multiple_linear_regression_model" src="https://user-images.githubusercontent.com/85929254/141708883-963de71d-64fb-4c03-b47c-b724a408ff51.png">

### Pre-Processing
The Processes Involved for Pre-Processing:
1. Checking data types for numerical values
2. Change data types of complexity object to Float
3. Finding the null values
4. Dropping the null rows
5. Finding duplicate entries
6. Using get_dummies on domain categories to get new columns with columns values
7. Checking the dataframe
8. Dropping the ID and Name
9. Transforming the values of owned users and users rated to smaller numbers to give the computer easier numbers to compare. This was done by dividing Users Rated by 1000 and Owned Users by 1000.

### Accuracy
After pre-processing, we found out that the accuracy of this model is 70% which is pretty accurate and precise, showing that the sensitivy is not too high.

### If There Was More Time
Something that I would have done was help with finding more stories from our data. What I mean by this is I would help Laura investigate other data that may have a possible correlation with average ratings that may have a high enough accuracy to analyze.
