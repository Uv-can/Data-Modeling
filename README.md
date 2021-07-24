# DATA MODELING

## Postgres ETL
    This project consists on putting into practice the following concepts:
    
    - Data modeling with Postgres,
    - Database star schema created,
    - ETL pipeline using Python
## Context
   
    A music company startup wants to analyze the data they havve been collecting on songs and user activity on their new music streaming app. 
    The analytics team is particularly interested in understanding what songs users are listening to.
    Currently, they do not have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, 
    as well as a directory with JSON metadata on the songs in their app.
    Your role is to create a database schema and ETL pipeline for this analysis.
### Data
    - **Song datasets**: all json files are nested in subdirectories under */data/song_data*. A sample of this files is:
    
    {\"num_songs\": 1, \"artist_id\": \"ARJIE2Y1187B994AB7\", \"artist_latitude\": null, \"artist_longitude\": null, \"artist_location\": \"\", \"artist_name\": \"Line       Renaud\", \"song_id\": \"SOUPIRU12A6D4FA1E1\", \"title\": \"Der Kleine Dompfaff\", \"duration\": 152.92036, \"year\": 0}
    
    - **Log datasets**: all json files are nested in subdirectories under */data/log_data*. A sample of a single row of each files is:
    
    {\"artist\":\"Slipknot\",\"auth\":\"Logged In\",\"firstName\":\"Aiden\",\"gender\":\"M\",\"itemInSession\":0,\"lastName\":\"Ramirez\",\"length\":192.57424,\"level       \":\"paid\",\"location\":\"New York-Newark-Jersey City, NY-NJ-PA\",\"method\":\"PUT\",\"page\":\"NextSong\",\"registration\":1540283578796.0,\"sessionId\":19,\"song     \":\"Opium Of The People (Album Version)\",\"status\":200,\"ts\":1541639510796,\"userAgent\":\"\\\"Mozilla\\/5.0 (Windows NT 6.1) AppleWebKit\\/537.36 (KHTML, like       Gecko) Chrome\\/36.0.1985.143 Safari\\/537.36\\\"\",\"userId\":\"20\"}
## Database Schema
    The schema used for this exercise is the Star Schema: 
    There is one main fact table containing all the measures associated to each event (user song plays),
    and 4 dimentional tables, each with a primary key that is being referenced from the fact table.
## How to run the Project
    
    1) Run in console
    python create_tables.py
    
    2) Used test.ipynb Jupyter Notebook to interactively verify that all tables were created correctly.
   
    3) Run etl in console, and verify results:
    
    python etl.py
