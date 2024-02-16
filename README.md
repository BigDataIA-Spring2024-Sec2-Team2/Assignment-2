## Live application Links
[![codelabs](https://img.shields.io/badge/codelabs-4285F4?style=for-the-badge&logo=codelabs&logoColor=white)](https://docs.google.com/document/d/1dZdiE4i6tSN4ORSth-93WU_VrgvxRuWhSNYANm2L1e4/edit#heading=h.30zowzpo6ptm/)
## Overview

## Problem Statement

The objective of this assignment is to develop a comprehensive data engineering solution that aggregates, structures, and makes accessible a vast array of finance professional development materials. This project will enhance the learning experience for finance professionals by providing an intelligent app interface to interact with curated finance materials.

## Project Goals
Task is to create two primary datasets from the 224 refresher readings listed on the C[CFA Institute's website](https://www.cfainstitute.org/en/membership/professional-development/refresher-readings#sort=%40refreadingcurriculumyear%20descending) and the topic outlines(attached PDF files). These readings are crucial for finance professionals looking to improve their finance skills. The datasets will serve as the backbone for an intelligent application designed for these professionals.

## Technologies Used
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)
[![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://www.python.org/)
[![AWS](https://img.shields.io/badge/AWS-411120?style=for-the-badge)](https://aws.amazon.com/)
[![SqlAlchemy](https://img.shields.io/badge/SqlAlchemy-700000?style=for-the-badge)](https://www.sqlalchemy.org/)
[![GROBID](https://img.shields.io/badge/GROBID-FFFFFF?style=for-the-badge&logo=GROBID&logoColor=black)](https://grobid.readthedocs.io/en/latest/Introduction/)
[![Snowflake](https://img.shields.io/badge/snowflake-0000FF?style=for-the-badge&logo=snowflake&logoColor=white)](https://docs.snowflake.com/ )

## Data Sources
[CFA Institute's website](https://www.cfainstitute.org/en/membership/professional-development/refresher-readings#sort=%40refreadingcurriculumyear%20descending)

## Pre requisites
1. Python Knowledge
2. Snowflake Account
3. AWS Keys

## Project Structure

```
📦 
├─ data
│  └─ extracted-pdf-data_Grobid
│  |  ├─ 2024-l1-topics-combined-2.grobid.tei
│  |  ├─ 2024-l2-topics-combined-2.grobid.tei
│  |  ├─ 2024-l3-topics-combined-2.grobid.tei
│  |  ├─ grobid_metadata.csv
|  |  ├─ grobid_metadata_new.csv
│  |  ├─ Grobid_RR_2024_1_combined.txt
│  |  ├─ Grobid_RR_2024_2_combined.txt
│  |  └─ Grobid_RR_2024_3_combined.txt
│  └─ extracted-pdf-data_PyPDF2
│  |  ├─ PyPDF_RR_2024_levelI_combined.txt
│  |  ├─ PyPDF_RR_2024_levelII_combined.txt
│  |  └─ PyPDF_RR_2024_levelII_combined.txt
|  └─ raw-pdf-data
|  |  ├─ 2024-l1-topics-combined-2.pdf
|  |  ├─ 2024-l2-topics-combined-2.pdf
|  |  └─ 2024-l3-topics-combined-2.pdf
|  └─ scrape-data
│      └─ cfa-data.csv
├─ diagrams
│  ├─ architecture_diagram.ipynb
│  └─ architecture_diagram
├─ logs
│  ├─ scrape-log
│  │  └─ webscrapping.log
│  └─ data-load-log
│     └─ snowflake-upload.log
├─ notebooks
│  └─ data-load
|  |   ├─ snowflake_helper.py
|  |   ├─ snowflake_upload.ipynb
│  |   └─ store-files.ipynb
│  ├─ pdf-data-extract
│  │  └─ pdf-data-extractionn.ipynb
│  └─ web-scrape
│     └─ webscrape_cfa.ipynb
├─ configuration.properties.example
├─ .gitignore
├─ README
└─ requirements.txt
```

## How to run Application locally

1. Create Python virtual environment
2. run -> pip install -r requirements.txt
3. load Jupyter Notebook
4. Copy configuration.properties.example and rename it to configuration.properties and add the keys
5. run local image of Grobid
6. run the webscrape_cfa.ipynb - file
7. next run pdf-data-extractionn.ipynb
8. then run snowflake_upload.ipynb
9. finally run store-files.ipynb
    
## Project run outline

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

## References

- https://www.crummy.com/software/BeautifulSoup/bs4/doc/
- https://www.selenium.dev/
- https://www.cfainstitute.org/en/membership/professional-development/refresher-readings#sort=%40refreadingcurriculumyear%20descending
- https://pypdf.readthedocs.io/en/stable/
- https://github.com/kermitt2/grobid
- https://diagrams.mingrammer.com/
- https://aws.amazon.com/
- https://app.snowflake.com/
- https://www.sqlalchemy.org/
- https://github.com/ashrithagoramane/DAMG7245-Spring24/tree/main/repository_structure

## Team Information 
Project Board - https://github.com/orgs/BigDataIA-Spring2024-Sec2-Team2/projects/1/views/1

Name | Contribution %| Contributions |
--- |--- | --- |
Anshul Chaudhary  | 40% | web scrapping, Snowflake setup/csv upload|
Agash Uthayasuriyan | 30% | Grobit locall installation and data extraction|
Narayani Arun Patil | 30% | Pypdf2 data extraction and text S3 upload|
