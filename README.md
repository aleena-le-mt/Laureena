# Creating the database
1. Open PGAdmin
2. Navigate to Databases
3. Right click to create a new database.
4. Name database "BoardGames"
5. Click "Save"
6. Create a config.py file that contains "db_password = 'YOUR PASSWORD for PGADMIN'"
7. Run all cells in "Sheena-DBCleanup" jupyter notebook. (If you get a "psycopg2 not found" error while running the notebook, go back into your terminal and run "pip install psycopg2-binary" then try again)

# Laureena: Board Games
# Board Games
## Segment 1 - Getting Started
### Project Overview
We have recently found some data on board games and decided to work on this topic because board game data is interesting and fun to work on with all the different ways in which people win and think about these games. Something that is different in board game data compared to other online games is how raw it can be. With online games, we only end up with data created through technology itself. However, with board games, we can ensure that the data that we collect are all from real life people playing these games without any form of technology being apart of it.

### Purpose
The purpose of this project is to analyze the various data points presented in the board game dataset and see if we can find any correlations between those data points on either the games' ratings or the games' complexity to create a model that could predict what makes a good game.

### Resources
- Raw Data: https://www.kaggle.com/andrewmvd/board-games/version/2
- Data Source: BoardGameGeek.com
- Software: Excel 365, Python 3.6.1, Tableau Desktop 2021.3, Tableau Public 2021.1

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

## Segment 3 - Visualizations
### Project Overview
This week, we focused on visualizations and how to make it interactive on Tableau. The data that we are using for these visualizations is the correlation between the games' rankings and complexity averages of our domains and comparing those domains with each other. When we say domains, we mean the types of games that will be shown in our interactive visualzation:
- Abstract Games
- Children's games
- Customizable Games
- Family Games
- Party Games
- Strategy Games
- Thematic Games
- Wargames

### Interactive Visualization
<img width="842" alt="Main_Visual_Graph" src="https://user-images.githubusercontent.com/85929254/143804918-8e8409f0-955a-4015-ad64-d0307542d561.png">
The main thing that makes this visualization interactive is clicking on the different game typs under Domain (Groups). By doing this, we will see and understand what ranking people give to these game types depending on how hard these games are (how complex they are).

### Purpose
The whole point of the work for this week is making sure that our visualization data has any correlation and figuring out what we need to separate and/or put together in order to see this correlation between average ratings, complexity averages, and our domains clearly. On top of that of all that, we needed to figure a way to make it all interactive.

### Questions To Answer
Questions that we hope to answer from our visualizations:
- What is the correlation between complexity averages and rating averages in Strategy Games?
- What is the correlation between complexity averages and rating averages in Abstract Games?
- What is the difference between the the correlation in Strategy Games and Abstract Games?
- Do people prefer Strategy Games or Abstract Games?
- Which type of game do people like the most out of all the games that we have?

### Challenge Summary
In the beginning, we had trouble thinking about how to turn our visualization with so many different specific game names attached together with their game types. Since this was the case, Sheena was trying to figure out how to condense these games into their own domains. To put it in simple words, how to seperate these game types and condense them into their own domain. This was something that was solved through the grouping function on Tableau where you would select the games with the same game types and group it altogether. After that, we were able to select the different game types and look at the relationship between rating averages and complexity averages in these different domains and compare these domains with the other domains that we have. The only problem that we had was downloading the desktop version of Tableau before Sheena's version of Tableau ends to show these visualizations when we present. This was solved when both Laura and I was able to get Tableau Desktop and download the visuals.

### If There Was More Time
If there was more time, I would try to delve deeper into what Laura's models have in common with these visuals because Laura has recently made more new machine learning models that I have yet to look into.

### Google Slides Outline
[Laureena Outline - Board Games.pdf](https://github.com/aleena-le-mt/Laureena/files/7585865/Laureena.Outline.-.Board.Games.pdf)

### Tableau Public DashBoards
https://public.tableau.com/app/profile/sheena.strohmayer/viz/BoardGames_16378156604150/BoardGames

## Segment 4 - Conclusion
### Conclusion
In general, the higher the rating average is, the higher the complexity average. As you may not be able to tell already, we decided to switch to using complexity average vs rating average because there was a more prominant correlation seen compared to complexity average vs ranking. Now for our main question, can we predict rating average based on other game variables? We cant predict rating average itself, but we can predict whether or not rating average is above or below average. From looking at all this use average rating data, we have decided that it is useful and important for mainly people who produce these types of board game. They would use this data to improve their board games and possibly create a different game with better features that are similar to their games that are included in this data. The main additional observation that we have is that the domain (game category) cannot be reasonably predicted using other game variables such as min/max players, complexity, average ratings, etc.


### If There Was More Time
If there was more time, we would try to see if there is a possible higher accuracy score for logistics regression from the visual with just the complexity average variable and the rating average compared to using all of the game variables since this scatter plot has a prominant correlation to look at. With more time, we can find a mroe accurate way to get rating average if we look into all of the available gaming variable, specifically the mechanics.
<img width="785" alt="RatingvsComplexityAverage" src="https://user-images.githubusercontent.com/85929254/144153200-cb74e20f-cc04-4c0a-99de-b88d170ce2d5.png">

### Final Google Slides


### Tableau Public DashBoards
https://public.tableau.com/app/profile/sheena.strohmayer/viz/BoardGames_16378156604150/BoardGames
