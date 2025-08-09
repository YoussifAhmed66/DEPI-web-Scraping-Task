# DEPI-web-Scraping-Task
DEPI web scraping task using Beautiful Soup Python library, Supervised by: Eng/ Baraa Abu Sallout.

---

## Overview

This repository contains a Python-based web scraping project that extracts specific data from the HTML page at `https://baraasalout.github.io/test.html` and processes it into structured formats (CSV and JSON). The project fulfills the requirements of a web scraping task, including extracting text data, table data, product information, form details, links, multimedia, and a scripting challenge for featured products.



## Repository Structure
- `WebScraping.ipynb`: Jupyter Notebook containing the Python script for web scraping.
- `Extract_Text_Data.csv`: CSV file with extracted headings (`<h1>`, `<h2>`), paragraphs (`<p>`), and list items (`<li>`).
- `Extract_Table_Data.csv`: CSV file with table data (Product Name, Price, Stock Status).
- `Product_Information.json`: JSON file with book card data (Book Title, Price, Stock Availability, Button Text).
- `Extract_Form_Details.json`: JSON file with form input details (Field Name, Input Type, Default Value, Placeholder).
- `Extract_Links.json`: JSON file with multimedia links (video and images).
- `Featured_Products_Data.csv`: CSV file with featured products data (Product Name, Hidden Price, Available Colors, Product ID).
- `README.md`: This file, providing an overview and detailed documentation.

## Prerequisites
To run the script, you need:
- Python 3.x
- Libraries: `requests`, `beautifulsoup4`, `csv`, `json`
- Install dependencies using:
```
pip install requests beautifulsoup4
```

## How to Run
1. Clone or download this repository
2. Open `WebScraping.ipynb` in Jupyter Notebook.
3. Run all cells to execute the scraping tasks and generate output files.
4. Output files (`*.csv`, `*.json`) will be created in the same directory.

## Project Details
### Approach
The project uses Python in a Jupyter Notebook (`WebScraping.ipynb`) with `requests` to fetch the HTML page and `BeautifulSoup` to parse it. The script is divided into functions for each task:
- __Text Data__: Extracts `<h1>`, `<h2>`,` <p>`, and `<li>` tags into `Extract_Text_Data.csv`.
- __Table Data__: Pulls Product Name, Price, and Stock Status from a <table> into `Extract_Table_Data.csv`.
- __Book Cards__: Gathers Book Title, Price, Stock Availability, and Button Text from `<div class="book-products">` into `Product_Information.json`.
- __Form Details__: Extracts input fields (e.g., name, type, value) from a `<form>` into `Extract_Form_Details.json`.
- __Multimedia__: Collects video (`<iframe>`) and image (`<img>`) links into `Extract_Links.json`.
- __Featured Products__: Extracts Product Name, Hidden Price, Colors, and Product ID from `<div class="products">` into `Featured_Products_Data.csv`.

### Tools Used
- __Python 3.13.5__: Main programming language.
- __Jupyter Notebook__: For writing and testing the script.
- __Libraries__:
  - `requests`: Fetches the HTML page.
  - `beautifulsoup4`: Parses HTML for data extraction.
  - `csv` and `json`: Save data to CSV and JSON files.

### Challenges Faced
- __Hidden Price__: The hidden price (`<span class="price">`) was easy to extract since `BeautifulSoup` ignores CSS `display: none`.
- __Form Inputs__: Filtering `<label>` tags and handling mixed input types (e.g., `<select>`, `<option>`) required careful attribute checks.
- __No `<a>` Tags__: The task asked for hyperlinks, but none existed, so the script handles only videos and images.
- File Encoding: Used UTF-8 encoding to handle special characters like `✔`.
