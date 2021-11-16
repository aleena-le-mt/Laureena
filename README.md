# Creating the database
1. Open PGAdmin
2. Navigate to Databases
3. Right click to create a new database.
4. Name database "BoardGames"
5. Click "Save"
6. Create a config.py file that contains "db_password = 'YOUR PASSWORD for PGADMIN'"
7. Run all cells in "Sheena-DBCleanup" jupyter notebook. (If you get a "psycopg2 not found" error while running the notebook, go back into your terminal and run "pip install psycopg2-binary" then try again)
