# DEND-data-modeling-with-postgres

## Summary

Process song and log data in json format and populate to a set of tables in star schema.

### Fact Table

`songplays` - records in log data associated with song plays i.e. records with page `NextSong`
- songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables

`users` - users in the app
- user_id, first_name, last_name, gender, level

`songs` - songs in music database
- song_id, title, artist_id, year, duration

`artists` - artists in music database
- artist_id, name, location, latitude, longitude

`time` - timestamps of records in songplays broken down into specific units
- start_time, hour, day, week, month, year, weekday

---

## Installation (for Mac)

1. Install Postgres.app and start server: 
https://postgresapp.com/

2. Create `studentdb`, and set up `student` role and permission:
    
    ```sql
    CREATE DATABASE studentdb;
    CREATE ROLE student WITH LOGIN PASSWORD 'student' CREATEDB;
    ```

3. Install Python dependencies

    ```bash
    pip install -r requirements.txt
    ```

4. Run `create_tables.py` to drop and recreate tables

    ```bash
    python create_tables.py
    ```

5. Run `etl.py` to perform ETL and populate data into tables

    ```bash
    python etl.py
    ```
