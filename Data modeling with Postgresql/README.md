# Sparkify Music Streaming Database

## Purpose
Sparkify, a burgeoning music streaming startup, has embarked on a mission to glean meaningful insights from the treasure trove of data they've amassed through their new music streaming application. Central to this endeavor is their aim to understand user behaviors and song preferences. With an expanding user base and a vast catalog of songs, Sparkify seeks to facilitate data-driven decision-making, personalized user experiences, and efficient content recommendation systems. To this end, they require a robust database and ETL (Extract, Transform, Load) pipeline that can handle the data analytics demands.

## Database Schema Design
In line with Sparkify's analytical goals, we've meticulously crafted a star schema database that optimizes queries for song play analysis. This design choice fosters simplicity, efficiency, and comprehensibility. 

### Repository Files:
1. **sql_queries.py**: This file contains SQL statements for creating and dropping tables, as well as inserting data into these tables.

2. **create_tables.py**: Running this script creates a new PostgreSQL database and the required tables by executing the SQL statements defined in sql_queries.py. Use this script to initialize the database.

3. **etl.ipynb**: This Jupyter Notebook provides detailed instructions for the ETL process. It includes step-by-step code and explanations for extracting data from JSON files, transforming it, and loading it into the database tables. This notebook is helpful for developing and testing the ETL pipeline.

4. **etl.py**: This script contains the ETL pipeline code that processes the entire datasets, populating the fact and dimension tables. It should be run after creating tables using create_tables.py.

5. **test.ipynb**: This Jupyter Notebook serves as a testing tool to confirm that data has been successfully inserted into the tables. It checks the correctness of the database schema and the completeness of data insertion.

### Running the Project:
Follow these steps to run the project:

1. **Create Tables**: Execute create_tables.py to create the PostgreSQL database and initialize the necessary tables. Make sure the database connection parameters are correctly set in this script.

2. **ETL Processes**: Open and follow the instructions in etl.ipynb. This notebook guides you through the ETL processes for each table (songplays, users, songs, artists, and time). At the end of each section or the notebook, run test.ipynb to confirm that data has been successfully inserted into the respective tables.

3. **ETL Pipeline**: After completing and verifying the ETL processes in etl.ipynb, run etl.py. This script automates the ETL process for the entire dataset. Remember to execute create_tables.py again before running etl.py to reset the tables.

## ETL Pipeline
Our ETL pipeline is the backbone of data preparation and integration into the database. It comprises the following stages:

1. **Extraction**: Data is sourced from two directories - JSON logs containing user activity and JSON metadata for songs. We extract the raw data from these sources.

2. **Transformation**: This stage involves data cleaning, parsing, and merging. We transform the raw data into a structured format suitable for storage in the database. For example, we join log data with song data to identify song plays accurately.

3. **Loading**: The transformed data is loaded into the appropriate tables within our PostgreSQL database. This process maintains referential integrity by using primary and foreign keys.

Our chosen schema and ETL pipeline are carefully crafted to empower Sparkify's analytical goals. This structure enables efficient querying for song play analysis, user behavior insights, and personalized recommendations. By fostering simplicity and performance, this database setup equips Sparkify with the tools needed to navigate the complex world of music streaming analytics effectively.
