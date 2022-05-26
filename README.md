# Nevada Real Estate Investment Opportunities
![image](https://github.com/AbsIbs/King_County_Project/raw/main/images/readme_image.png)

## Table of Contents
- <a href="#business-case">Business Case</a>
- <a href="#requirements">Requirements</a>
- <a href="#installation">Installation</a>
- <a href="#demo-and-usage">Demo and Usage</a>
- <a href="#dataset">Dataset</a>
- <a href="#exploratory-data-analysis">Exploratory Data Analysis</a>
- <a href="#modelling">Modelling</a>
- <a href="#model-performance">Model Performance</a>
- <a href="#conclusion">Conclusion</a>

## Business Case
As Three Modellers Consulting, we have a long background in Data Science with successful anayses and building machine learning models. The nature of the project is thus **Time Series Modelling**.

PLM Real Estate has consulted us with the question:<br/>
**What are the top 5 best zip codes for us to invest in?**<br><br>
This would be determined by which zipcode has the best predicted **ROI**(return on investment).

## Requirements
This project assumes you already have these system dependencies set up:
- **Python 3.8.5**
- **pip**
- **Conda environment set-up**

## Installation
As all the dependencies are stored in the **requirements.txt** file, running this command in your bash/terminal  <br>
```bash
pip: -r requirements.txt
```

## Demo and Usage
Our findings from the project has been visualised in the form of an interactive [dashboard](https://public.tableau.com/app/profile/abs4364/viz/NevadaTimeSeriesAnalysis/Dashboard) made by tableau.
<br><br>
![image]()

## Dataset
- Source: **Zillow Housing dataset**
- Over 14,000 zipcodes
- Period: **Apr 1996 - Apr 2018**
- Additional fetures: microeconomic features web scraped data from **www.UnitedStatesZipCodes.org** & macroeconomic features gathered from Fred [Economic Data](https://fred.stlouisfed.org/)

## Methodology
As predicting the future house prices of 14,000 zipcodes would prove too time-consuming, only the top zipcode that had the largest ROI over the last 5 years worth of data (2013 - 2018) were analysed. When investigated, it was found that **Nevada** zipcodes yielded the largest ROI.
![image]()

## Exploratory Data Analysis
Having established **Nevada** our the focus of the project, the first part of the EDA examined the general trend of the ROI was examined. Naturally, it revealed a losses around 2008 due to the recession.

## Modelling
### Feature Engineering
To maximise the performace of the models, large amounts of exogenous variable in the form of **micro/macroeconomic** variables.


