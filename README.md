# Project: Data Modeling with Postgres

------------------------------------------
### Purpose of database
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.
As a data engineer, I need to create a database schema and ETL pipeline for this analysis so that analytics team can easily query the data they require.

--------------------------------------------

#### Fact Table 
1. **songplays** - records in log data associated with song plays i.e. records with page `NextSong` 
    + *songplay_id (PK), start_time , user_id , level, song_id , artist_id , session_id, location, user_agent*

#### Dimension Tables 
2. **users** - users in the app 
    + *user_id (PK), first_name, last_name, gender, level*

3. **songs** - songs in music database
    + *song_id (PK), title, artist_id, year, duration*

4. **artists** - artists in music database
    + *artist_id (PK), name, location, lattitude, longitude*

5. **time** - timestamps of records 
    + *start_time (PK), hour, day, week, month, year, weekday*

--------------------------------------------
### Project Structure 
In addition to the data files, the project includes six files:
+ `test.ipynb` - This notebook is used to check on the database;
+ `create_tables.py` - This script will drop and create the tables;
+ `etl.ipynb` - This notebook reads and processes files from data and loads them into the tables;
+ `etl.py` - This script is our ETL script which will allow us to read the data from JSON files , parse them and insert into the corresponded table;
+ `sql_queries.py` - This script contains all your sql queries, and is imported into the last three files above.

--------------------------------------------
### Running procedure

1. Run `create_tables.py` from the Terminal to create the 'sparkifydb' database and tables.
2. Run 'etl.ipynb' to get data from files and then insert the data into tables.
3. Run test.ipynb to confirm your records were successfully inserted into each table.

