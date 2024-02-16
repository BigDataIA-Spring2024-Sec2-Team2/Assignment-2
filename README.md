# Assignment-2

### Overview
This project aims to create two primary datasets by scraping information from the [CFA Institute's website](https://www.cfainstitute.org/en/membership/professional-development/refresher-readings#sort=%40refreadingcurriculumyear%20descending) and extracting text from provided PDF files. Ensuring that the data is successfully uploaded to the cloud.

### 1. Web Scraping and Dataset Creation

- Run the notebook webscrape_cfa.ipynb. This notebook will scrape data using Beautiful Soup library from the CFA Institute's website
- Structured scrapped data into a CSV file with schema {Name of the topic, Year, Level, Introduction Summary, Learning Outcomes, Link to the Summary Page, Link to the PDF File}, and automate the process using Python.

### 2. PDF Extraction
- Run the notebook pdf-data-extraction.ipynb. This notebook will extract text from PDF files using PyPDF2 and Grobid, organizing the output into separate text files.
  
### 3. Database Upload
- Run the notebook store_files.ipynb. This notebook utilizes SQLAlchemy to upload structured data from Step 1 into a Snowflake database.

### 4. Cloud Storage Integration
- Run the notebook couldStorage.ipynb. This notebook contains a Python function to upload CSV (Data received by web scraping) and text files (Data received by processing pdf files) to an AWS S3 bucket.
- It also updates the Snowflake database i.e. utilizing SQLAlchemy to upload the structured metadata from step 2 (data received by processing pdf files with Grobid).

CodeLab - [Documentation](https://docs.google.com/document/d/1dZdiE4i6tSN4ORSth-93WU_VrgvxRuWhSNYANm2L1e4/edit#heading=h.30zowzpo6ptm) 

## Authors

| Name            | Email                     |
| --------------- | --------------------------------- |
| Anshul Chaudhary        | chaudhary.ans@northeastern.edu |
| Agash Uthayasuriyan     | uthayasuriyan.a@northeastern.edu |
| Narayani Arun Patil     | patil.nar@northeastern.edu |
