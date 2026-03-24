# real-estate-scraping-pipeline-cyprus
Web scraping pipeline for real estate listings (101evler.com) using Selenium, overcoming Cloudflare protection to analyze price per m².

North Cyprus Real Estate Data Pipeline
Project Overview

This project builds a data pipeline to collect and analyze real estate listings from 101evler.com, focusing on properties in Northern Cyprus.

The goal is to extract key property data and analyze price per square meter (m²) to identify market trends and potential opportunities.

Data Source

Data is collected from:

https://www.101evler.com

The platform contains dynamic listing pages protected by Cloudflare, which makes automated data extraction challenging.

Technologies Used
Python
Pandas
Selenium
SQLite
Matplotlib
Challenges & Approach
Cloudflare Protection

The website is protected by Cloudflare anti-bot mechanisms, which caused:

"Just a moment..." verification pages
Random page load failures
Browser sessions being blocked

To overcome this:

Pages were loaded using Selenium (real browser automation) instead of direct requests
Delays and controlled navigation were added
In some cases, the browser was restarted between pages to reduce blocking
Why Not BeautifulSoup?

Initially, BeautifulSoup was considered, but it was not suitable because:

The site loads content dynamically with JavaScript
Direct HTTP requests were blocked by Cloudflare
Required data is not available in static HTML responses

Therefore, Selenium was used to interact with the fully rendered page.

Data Pipeline

The pipeline follows these steps:

1. Collect Listing Links
Navigate through multiple pages
Extract all property URLs
2. Extract Property Details

From each listing:

Price
Property size (m²)
Location
Listing date
Update date
Number of rooms
Building age
Furnishing status
3. Data Cleaning
Convert prices to numeric format
Standardize m² values
Handle missing or inconsistent fields
Remove invalid listings
4. Feature Engineering
Calculate price per m²
Create cleaned and structured dataset for analysis

Example Use Cases

This dataset can be used to:

Analyze average price per m² by region
Identify undervalued properties
Track market trends over time
Support investment decisions

How to Run

Install dependencies:

pip install selenium pandas matplotlib

Run the notebook:

101lastweek.ipynb
Notes

Due to Cloudflare protection, scraping stability may vary.
The pipeline is designed with workarounds, but occasional failures may still occur.

Author

Çağrı 

Data Science projects focused on:

Data pipelines
Web scraping
Market analysis
Machine learning
