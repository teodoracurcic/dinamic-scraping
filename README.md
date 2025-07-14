# Homework: Browser Automation with Playwright

This assignment was completed as part of coursework for the [Lede Program at Columbia Journalism School](https://ledeprogram.com).  
The goal was to use browser automation techniques in Python to scrape structured data from a dynamic government website using Playwright.

The project focused on retrieving trademark data from the United States Patent and Trademark Office (USPTO) for a specific company (Nike), including serial numbers and image links for all currently active trademarks.

## Notebook

**File**: `browser-automation-hw-v2.ipynb`  
This notebook includes the full workflow: opening a browser with a custom user agent, submitting a query, navigating through paginated results, saving HTML pages, and parsing them into structured data using XPath.

## Website Targeted

- [USPTO TESS Trademark Search](https://tmsearch.uspto.gov/search/)  
  Search conducted for all active trademarks owned by Nike, using filters to exclude inactive ("dead") records.

## Data Collected

- **Serial number** of each trademark  
- **Image URL** associated with the trademark

Data was extracted from paginated search result pages, saved as local HTML files, then parsed using `lxml` and stored in a DataFrame. Final results were saved as a CSV file (`data/trademarks.csv`) containing 350 entries.


## Tools & Techniques

- `playwright.async_api` — for automating browser interaction
- `XPath` — for locating elements and extracting content
- `lxml.html` — for parsing saved HTML files
- `pandas` — for structuring and exporting data

The automation was run in non-headless mode to allow manual CAPTCHA resolution if required.