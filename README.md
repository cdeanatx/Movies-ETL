# Movies ETL

## Overview of Project

The purpose of this project is to create an automated ETL pipeline for the Amazing Prime Hackathon contest.

## Datasets

There were 3 data sources that needed to be cleaned and merged:

1. Wikipedia JSON - This data was acquired by web-scraping Wikipedia sidebars.
2. Movie Metadata CSV - This data was compiled from IMDB and acquired from Kaggle.
3. Ratings CSV - This data was compiled from Metacritic and acquired from Kaggle.

## Summary of Project

The steps taken to clean and merge the aforementioned datasets were as follows:

1. Read in files to Pandas.
2. Combine wiki columns that were similar (`Directed by` was combined with `Director` and other similar combinations).
3. Drop wiki columns that had insufficient data points.
4. Use regex to format numeric and date columns uniformly.
5. Drop metadata columns that were unnecessary.
6. Update data types for numeric/datetime columns in metadata.
7. Merge wiki and metadata.
8. Identify duplicate columns from wiki and metadata.
9. Fill in missing values from metadata, where wiki values were not null.
10. Drop the wiki columns that were duplicated because metadata had more consistent data.
11. Format ratings to show count of different ratings for each movie (used pivot).
12. Merge ratings with wiki/metadata.
13. Export data to PostgreSQL.