# JSE PDF Scraper

This repository documents a project that automates the collection and extraction of publicly available PDF reports from the Jamaica Stock Exchange (JSE). The goal is to streamline the process of gathering stock-related data for analysis, reporting, and database integration.

# Key Features

Automated PDF Download
- Fetches publicly available reports from the JSE website.

Data Extraction
- Parses PDF content using regular expressions to extract stock prices, volumes, and company information.

Data Cleaning & Structuring
- Normalizes and organizes extracted data into tabular formats for analytics.

Output
-Saves processed data to Excel for reporting or further analysis.


## Workflow

1. **Download PDFs**  
   - Automatically fetches publicly available PDFs from the JSE website.

     # Example : Download the PDF using requests
        ```python
        response = requests.get(full_download_url)
        if response.status_code == 200:
            pdf_file_path = os.path.join(pdf_folder_path, f"price_history_{instrument_code}_{today_date}.pdf")

             with open(pdf_file_path, "wb") as file:
                file.write(response.content)
            print(f"PDF for instrument code {instrument_code} on {today_date} downloaded successfully: {pdf_file_path}")
        else:
            print(f"Failed to download PDF for instrument code {instrument_code}. Status code: {response.status_code}")
        ```

2. **Extract Data from PDFs**  
   - Parses PDF content using text extraction techniques.
   - Uses **regular expressions (regex)** to extract relevant financial data such as stock prices, volumes, and company information.

      ```python
      import re

      Example: regex for a row with Date, Instrument, and Volume
      row_pattern = re.compile(r"(\d{4}-\d{2}-\d{2})\s+([A-Za-z0-9]+)\s+(\d+)")
      ```
     

3. **Data Cleaning and Structuring**  
   - Cleans and normalizes the extracted data.
   - Structures data into a tabular format suitable for analysis or database ingestion.

4. **Output**  
   - Saves the processed data to CSV or Excel for reporting and further analytics.
  

Notes
All PDFs used are publicly available.
The actual scraping and extraction code is proprietary and not included for monetization purposes.
Dummy examples and workflow documentation are provided to illustrate methodology and expected outputs.
