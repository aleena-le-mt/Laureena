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
## Project Overview
We have recently found some data on board games and decided to work on this topic because board game data is interesting and fun to work on with all the different ways in which people win and think about these games. Something that is different in board game data compared to other online games is how raw it can be. With online games, we only end up with data created through technology itself. However, with board games, we can ensure that the data that we collect are all from real life people playing these games without any form of technology being apart of it.

## Purpose
The purpose of this project is to analyze the various data points presented in the board game dataset and see if we can find any correlations between those data points on either the games' ratings or the games' complexity to create a model that could predict what makes a good game.

## Resources
- Raw Data: https://www.kaggle.com/andrewmvd/board-games/version/2
- Data Source: BoardGameGeek.com
- Software: Excel 365, Python 3.6.1

## Description & Links of Datasource
The website "BoardGameGeek.com" allows users to rank board games on a scale of 1-10, and the site presents an average rating based on those individual ratings. This data is a collection of all ranked games in the BGG database.

## Questions To Answer
We hope to be able to answer questions related to game ratings and complexity such as...
- How complex the games are according to people's ratings of the games?
- What are the games' maximum amount of players?
- What are the games' average play time?
- What are the games' average complexity?
- Can we reasonably and accurately predict the average game rating?

## Challenge Summary
Things we had trouble with:
- Finding a dataset that is reliable and interesting to work on. 
- Getting our data into pgAdmin because when we tried running the data in Jupyter Notebook, there was an error saying "psycopg2" does not exist. We were able to resolve this by putting in "pip install psycopg2-binary" into the pythondata terminal that we used to open Jupyter Notebook. 
- The first learning model produced predictions that were not within a normal range of the other predictions or the dataset "Rating Averages". The describe function used on features showed "Years Published" had values in the negative such as -3500. All data with "Years Published" before 1800 was removed before training and testing the model. The new dataframe produced a new scatter plot without extreme outliers.

## Communication Protocols
We reach out to each other on Slack and decided on a day and time in which we all agreed to meet up on each week from now on, 3PM on Fridays. Whenever a question arises, we would ask eachother and if we all end up not knowing the answer, then we ask our captain, Savannah.
