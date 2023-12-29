# The GEF Project Data Scraper for Women in Data 2023 Hackathon

## Overview
This Jupyter notebook demonstrates a web scraping solution using Python to extract project information from the Global Environment Facility (GEF) website. The information includes project titles, funding institutions, implementing institutions, countries, regions, status, total project amount, links to project documentation, start dates, and end dates.

## Dependencies
Make sure you have the following Python libraries installed before running the notebook:

- BeautifulSoup
- lxml
- requests
- pandas
- numpy
- csv
- concurrent.futures
- re
- decimal

You can install these dependencies using the following:

    ```bash
    pip install beautifulsoup4 lxml requests pandas numpy
    ```

## Usage
1. Replace the `base_url` variable with the URL of the GEF website you want to scrape. Adjust the `num_pages` variable based on the number of pages you want to scrape.

    ```python
    # Replace with the URL of the website you want to scrape
    base_url = 'https://www.thegef.org/projects-operations/database?f%5B0%5D=focal_areas%3A2207&search=&page={}'
    ```

2. Run the first code cell to extract project links. This involves looping through the specified number of pages and collecting links to individual project details.

3. Run the second code cell to extract project general information. This step includes handling retries and exceptions during the scraping process. The information is then stored in a list of dictionaries (`project_info_list`).

4. Run the third code cell to create a DataFrame from the collected project information and export it to a CSV file named `thegef_data.csv`. The CSV file includes fields such as project title, funding institution, implementing institution, country, region, status, total project amount, link to project documentation, start date, and end date.

## Notes
- The code utilizes multithreading (`concurrent.futures.ThreadPoolExecutor`) for parallel scraping to improve efficiency.
- The `scrape_project_info` function handles exceptions and retries, ensuring robustness during the scraping process.
- The extracted data is stored in a CSV file for further analysis or download.

Feel free to adapt the notebook for your specific needs, and ensure compliance with the terms of use of the target website.


