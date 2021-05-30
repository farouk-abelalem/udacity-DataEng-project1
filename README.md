                                                            Data Modeling with Postgres
                    
Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. 

purpose of the project:
the purpose of this project is to model the data into a shape that simplifies the process of query and analysis.

Schema for the project:
Using the song and log datasets to create a star schema optimized for queries on song play analysis. This includes the following tables.

Fact Table
songplays - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

Dimension Tables
users - users in the app
user_id, first_name, last_name, gender, level
songs - songs in music database
song_id, title, artist_id, year, duration
artists - artists in music database
artist_id, name, location, latitude, longitude
time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

python scripts:

sql_queries.py: this file contains all queries that we use to delete previous schema if it exists, create new tables, and insert the data extracted from data files into the database.

create_tables.py: this files contains the python methods that uses sql_queries.py to delete any previous schema then create new schema with the tables we need.

etl.py: this file contains the methods that we use to extract the data from data files and insert it into database.

usage:
first run craete_tables.py to intiate the schema and create tables

second run etl.py to extract the data from files and ingest them into the database