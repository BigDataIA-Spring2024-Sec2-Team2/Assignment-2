## Live application Links
[![codelabs](https://img.shields.io/badge/codelabs-4285F4?style=for-the-badge&logo=codelabs&logoColor=white)](https://docs.google.com/document/d/1dZdiE4i6tSN4ORSth-93WU_VrgvxRuWhSNYANm2L1e4/edit#heading=h.30zowzpo6ptm/)
## Overview

This project aims to create two primary datasets by scraping information from the [CFA Institute's website](https://www.cfainstitute.org/en/membership/professional-development/refresher-readings#sort=%40refreadingcurriculumyear%20descending) and extracting text from provided PDF files. Ensuring that the data is successfully uploaded to the cloud.

## Technologies Used
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)
[![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://www.python.org/)
[![AWS](https://img.shields.io/badge/AWS-411120?style=for-the-badge)](https://aws.amazon.com/)
[![SqlAlchemy](https://img.shields.io/badge/SqlAlchemy-700000?style=for-the-badge)](https://www.sqlalchemy.org/)
[![GROBID](https://img.shields.io/badge/GROBID-FFFFFF?style=for-the-badge&logo=GROBID&logoColor=black)](https://grobid.readthedocs.io/en/latest/Introduction/)
[![Snowflake](https://img.shields.io/badge/snowflake-0000FF?style=for-the-badge&logo=snowflake&logoColor=white)](https://docs.snowflake.com/ )



## Data Sources
[CFA Institute's website](https://www.cfainstitute.org/en/membership/professional-development/refresher-readings#sort=%40refreadingcurriculumyear%20descending)


## Project Structure

```
📦 
├─ data
│  └─ extracted-pdf-data_Grobid
│     ├─ 2024-l1-topics-combined-2.grobid.tei
│     ├─ 2024-l2-topics-combined-2.grobid.tei
│     ├─ 2024-l3-topics-combined-2.grobid.tei
│     ├─ grobid_metadata.csv
│     ├─ Grobid_RR_2024_1_combined.txt
│     ├─ Grobid_RR_2024_2_combined.txt
│     └─ Grobid_RR_2024_3_combined.txt
│  └─ extracted-pdf-data_PyPDF2
│     ├─ PyPDF_RR_2024_levelI_combined.txt
│     ├─ PyPDF_RR_2024_levelII_combined.txt
│     └─ PyPDF_RR_2024_levelII_combined.txt
|   └─ raw-pdf-data
|      ├─ 2024-l1-topics-combined-2.pdf
|      ├─ 2024-l2-topics-combined-2.pdf
|      └─ 2024-l3-topics-combined-2.pdf
|    └─ scrape-data
│      └─ cfa-data.csv
├─ diagrams
│  ├─ architecture_diagram.ipynb
│  └─ architecture_diagram
├─ logs
│  ├─ scrape-log
│  │  └─ webscrapping.txt
├─ notebooks
│  ├─ data-load
│  │  └─ store-files.ipynb
│  ├─ pdf-data-extract
│  │  └─ pdf-data-extractionn.ipynb
│  └─ web-scrape
│     └─ webscrape_cfa.ipynb
├─ venv
├─ .gitignore
├─ README
└─ requirements.txt
```
Generated using [Project Tree Generator](https://woochanleee.github.io/project-tree-generator)


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

Name | Contributions |
--- |--- |
Anshul Chaudhary | 40 % |
Agash Uthayasuriyan | 30 % |
Narayani Arun Patil | 30 % |
