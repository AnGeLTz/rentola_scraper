# Rentola Scraper

## Overview

The Rentola Scraper is a Python-based web scraper designed to gather real estate data from specified URLs utilizing playwright library, store the information in a JSON file, and populate an SQLite database with the collected data.

## Project Structure

The project structure is organized as follows:

- **database_scripts**: Contains scripts related to the SQLite database.
  - `db_init`: Initializes the table rentola SQLite database.
  - `populate_db.py`: Populates the database with data from the JSON files in the "listings" folder.

- **database**: Contains the SQLite database.
  - `properties.db`: The SQLite database file.

- **rentola_scraper_scripts**: Contains the main scraping scripts.
  - `rentola_get_daily.py`: Gathers new URLs for scraping.
  - `rentola_parse_listing.py`: Extracts data from the scraped URLs and stores it in JSON files within the "listings" folder. You can modify chunk_size in line 250 to change the number of urls will be scraped concurrently. 

- **listings**: Contains subfolders named with dates (e.g., "2024-03-05") where scraped data is stored in JSON files.

- **scrape_populatedb.sh**: Bash script to execute the scraping and database scripts in sequence.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/AnGeLTz/rentola_scraper.git
    cd rentola_scraper/rentola_scraper
    ```

2. Build and run the Docker container:

    ```bash
    docker-compose up
    ```	

##In case of syntax error: unexpected end of file:
    ```bash
	docker-compose stop
	docker-compose down
        git rm --cached -r .
	git reset --hard
	docker-compose up
        ```

