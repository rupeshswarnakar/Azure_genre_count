# Movies Analytics using Azure Data Factory

## Project Overview
This project demonstrates an end-to-end ETL pipeline built using **Azure Data Factory** to process movie datasets. The pipeline ingests movie and rating data, transforms genre information, and loads aggregated insights into **Azure SQL Database**.


## Architecture
- **Source**: CSV files (`movies.csv`, `ratings.csv`)
- **Storage**: Azure Data Lake Storage Gen2
- **Processing**: Azure Data Factory (Mapping Data Flow)
- **Sink**: Azure SQL Database


## Data Pipeline Flow

1. Load movie and rating datasets into Azure Data Lake
2. Join datasets using `movieId`
3. Filter records where rating > 2
4. Split `genres` column using `|`
5. Flatten array into individual genre rows
6. Clean and transform genre values
7. Aggregate total count per genre
8. Load results into Azure SQL Database
