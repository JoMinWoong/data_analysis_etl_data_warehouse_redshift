# Introduction
This project processes the data in files in S3 to the stage tables on Redshift database and insert data to the analytics tables to enable analysis. 

# Datasets
This project uses 2 kind of data in S3 buckecks. one is song data and another one is log data.


# Data Schema
## Staging Table
### staging_songs - info about songs and artists
### staging_events - actions done by users (which song are listening, etc.. )

## Fact Table
- songplays - records in event data associated with song plays i.e. records with page NextSong
## Dimension Tables
- user - users in the app
- time - time data for log
- song - songs in music database
- artist - artists in music database

ER Diagram: 
 redshift_data_warehuse_music.png

# ETL Pipeline
- Created tables to store the data from S3 buckets.
- Loading the data from S3 buckets to staging tables in the Redshift Cluster.
- Inserted data into fact and dimension tables from the staging tables.

# Project Structure
- create_tables.py - This script will drop old tables (if exist) ad re-create new tables.
- etl.py - This script executes the queries that extract JSON data from the S3 bucket and ingest them to Redshift.
- sql_queries.py - This file contains variables with SQL statement in String formats, partitioned by CREATE, DROP, COPY and INSERT statement.
- dhw.cfg - Configuration file used that contains info about Redshift, IAM and S3

# How to Run
run `run.ipynb` file
