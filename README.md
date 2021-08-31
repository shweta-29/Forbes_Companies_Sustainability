Forbes Companies Sustainability Metrics
# Companies_Sustainability_Information
![image](https://user-images.githubusercontent.com/86231288/131497638-3a32eceb-b610-455c-ac8e-6c11816fb856.png)

This repository is created to build a dataset of Forbes 2021 2000 companies' financial metrics and ESG and CSR metrics. The ESG information has been collected from 5 different publically available data analytics firm. The websites used for ESG metrics are: S&P Global, MSCI, Yahoo Finance, CSR Hub, SustainAnalytics. The website used to collect financial information is Yahoo Finance.

The motivation behind this webscraping project is to gather the publically available data on ESG and financial metrics, and decipher if there is a relation between company's financial status with its performance in Sustainability.

The dataset generated contains 2000 rows with all the Forbes 2000 companies with 28 columns containing company info, its financial info and its ESG ratings

Selenium is used to scrape all the websites. 1_Forbes2000.py is the first file to be run. All other files can be run in any preference. Below is the information of each of the .py files:

Scraper.py This Python file serves as an input for all the other .py files. It has a Class that includes all the methods that are used commonly in all the .py files.

1_Forbes2000.py This file scrapes the companies name listed on Forbes 2000 website. Along with that information such as Country, Sales, Profit, Asset, and Market value of the companies is also collected. The output of this code is used as an input for all of the below files.

2_SP_ESG.py This file collects ESG score and supporting information such as Industry, Ticker, Country, Company Name (to tally with input Forbes dataset) from the S&P Global website

3_MSCI_ESG.py This file collects ESG ratings and supporting information such as Company name (to tally with input Forbes dataset) from the MSCI website

4_CSR.py This file collects CSR ratings and supporting information such as Company name (to tally with input Forbes dataset) from the CSR Hub website

5_SA_ESG.py This file collects ESG risk ratings and supporting information such as Company and Industry name from the SustainAnalytics website

6_Yahoo.py This file collects ESG ratings and financial metrics such as Market Cap, P/E, return on aset, Debt/equity, Operating Cash Flow and Stock Price from the Yahoo Finance website


This repository is created to build a dataset of companies' financial metrics and its corresponding ESG and CSR metrics. The ESG information has been collected from 5 different publically available data analytics firm. The websites used for ESG metrics are: S&P Global, MSCI, Yahoo Finance, CSR Hub, SustainAnalytics. The website used to collect financial information is Yahoo Finance. 

**Project Motivation**

This package is for investors interested in Sustainable Finance. The package can be used to gather the publically available data on ESG and financial metrics. This can help investors to choose a company based on its sustainability as well as financial performance. This data can be further used to decipher if there is a relation between company's financial status with its performance in Sustainability. 

![image](https://user-images.githubusercontent.com/86231288/131498205-c524ef28-9964-44bd-aaca-e51898dc4b6c.png)

**Package structure:**

WebScraping 

    - CompaniesESGmetrics

        -- esgscraper

            --- __init__.py
            --- esgdata.py
            --- scraper.py 
            --- csrhub.py
            --- snp_global.py
            --- msci.py
            --- sustainanalytics.py
            --- yahoo.py

        -- rds_uploader
            --- __init__.py
            --- rds_module.py
            
    - tests
    - Forbes.csv
    - .gitignore
    - LICENSE
    - README.md
    - setup.cfg
    - setup.py

**How to use**

1. Run esgdata.py. Enter the inputs.
2. Wait for the output! You will notice a .csv file created that gets appended as new informatin is scraped 
 
**Package details**

![image](https://user-images.githubusercontent.com/86231288/131498967-04673d9d-98f6-4a7d-bae2-aa6edff33e47.png)


Selenium is used to scrape all the websites. Below is the information for each of the .py files:

    1. esgdata.py: To begin, run this file. It will ask for these inputs: 
        a) Path of the file(.csv) that contains companies name
        b) Header name of the companies column
        c) Which website to scrape the data from: SustainAnalytics, S&P Global, CSR HUB, MSCI, Yahoo

    2. scraper.py This Python file serves as an input for all the other .py files. It has a Class that includes all
       the methods that are used commonly in all the .py files.

    3. snp_global.py : This file collects ESG score and supporting information such as Industry, Ticker, Country,
        Company Name from the S&P Global website. https://www.spglobal.com/esg/scores/

    4. msci.py : This file collects ESG rating and Company name from the MSCI website. 
       https://www.msci.com/our-solutions/esg-investing/esg-ratings/

    5. csrhub.py : This file collects CSR rating and Company name from the CSR Hub website.
        https://www.csrhub.com/search/name/

    6. sustainanalytics.py : This file collects ESG risk rating, Company and Industry name
        from the SustainAnalytics website. https://www.sustainalytics.com/esg-ratings

    7. yahoo.py : This file collects the below information from the Yahoo Finance website
        (https://finance.yahoo.com/lookup):
        ESG rating, company name and financial metrics such as Market Cap, Trailing P/E, return on asset, 
        Total Debt/Equity (mrq), Operating Cash Flow and Stock Price, Price/Book (mrq), Most Recent Quarter (mrq),
        Profit Margin, Op_Margin, return on equity, Diluted EPS, PayoutRatio

    8. rds_module.py: Use the class RdsUploader to upload the data to SQL database. Inputs needed: DATATBASE_TYPE, 
        DBAPI, ENDPOINT, PORT, DATABASE, USERNAME, PASSWORD. 
        Functions: create_table, send_query, read_table, add_rows, delete_row 

**Example dataset**

An example dataset of Forbes 2021 2000 companies is provided with this package.

![image](https://user-images.githubusercontent.com/86231288/131498320-e82e70a3-07c6-4088-986a-0b9695e9b81a.png)

**Things to note:**

    1. Enter a file path that contains the file name with the extension .csv
    2. Company names are extracted from each website so that the user can tally the company names with input companies
        names dataset 
    3. Check the documentation of each script for more information

License:
MIT © Shweta Yadav

Support:
For any questions and suggestions, connect with me on LinkedIn:  http://www.linkedin.com/in/shweta-yadav1
