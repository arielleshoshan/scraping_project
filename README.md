# scraping_project
 A scrape of missing persons in Florida.
 
Florida Missing Persons Scraper
This Python script is designed to scrape the Florida Missing Person Search website (https://www.fdle.state.fl.us/MCICSearch/Search.asp) to extract the details of all missing persons listed on the site and store the data in a CSV file.

Functions:

1. extract_data:
The extract_data function is responsible for extracting the missing person data from the table using Beautiful Soup. It takes two parameters: driver and data_list. The function extracts the HTML source code, parses it using Beautiful Soup, finds the table element by its class, loops through the rows and extracts the data for the 2nd, 3rd, and last cells from the missing data table, saves each missing person's data as a list, and appends it to the main data_list.

2. next_page
The next_page function is responsible for using a for loop to jump to the next page and extract data for the particular page. It takes one parameter: driver. The function uses Select() to get the select drop-down menu for the next page, extracts data by calling extract_data and appending the current page data to data_list, waits for 1 second, and continues to the next page. The function stops at the last page and extracts the missing persons data from it.

3. create_missing_person_csv
The create_missing_person_csv function is responsible for creating a CSV file and writing the missing person data to it. It takes one parameter: data. The function removes the first three elements from the data list, opens a new file for writing, creates a CSV writer object, writes the header row, loops through the data list and writes each row to the CSV file. The function ignores incomplete data and prints a message when the CSV file is created successfully.

Usage:
To use this script, you will need to have Python and the following Python packages installed:

selenium
webdrivermanager
beautifulsoup4
requests
