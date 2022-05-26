# Nevada Real Estate Investment Opportunities
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/nevada.png)

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
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/nevada_project_image.png)

## Dataset
- Source: **Zillow Housing dataset**
- Over 14,000 zipcodes
- Period: **Apr 1996 - Apr 2018**
- Additional fetures: microeconomic features web scraped data from **www.UnitedStatesZipCodes.org** & macroeconomic features gathered from Fred [Economic Data](https://fred.stlouisfed.org/)

## Methodology
As predicting the future house prices of 14,000 zipcodes would prove too time-consuming, only the top zipcode that had the largest ROI over the last 5 years worth of data (2013 - 2018) were analysed. 
When examining the zipcodes on a state-level, it was found that **Nevada** zipcodes yielded the largest ROI with **64.7%.**
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/map.png)

Interestingly, it was also found that the 5 year ROI was largest on the west coast and decreased as you head towards the east.

Additionally, we can view the top 5 states in terms of 5 year ROI.
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/top_5_zipcodes.png)

Overall, this left just under 100 zipcodes to model.

## Exploratory Data Analysis
Having established **Nevada** our the focus of the project, the first part of the EDA examined the general trend of the ROI was examined. Naturally, it revealed a losses around 2008 due to the recession.
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/nv_roi_graph.png)

## Modelling
### Feature Engineering
To maximise the performace of the models, large amounts of exogenous variable in the form of **micro/macroeconomic** variables.
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/exogenous_variables.png)

### Models
The project used the following models:
- Neural Network Architectures (**LSTM | GRU | CNN**)
- SARIMAX Model
- Facebook Prophet Model

With the Neural Network models, a single model only 1 model was made to model all of the zipcodes. In contrast, the Facebook Prophet and SARIMAX models required a separate model for each zipcode to be made.

With predictions, the models are simply aiming to predict the next month's average house price per zipcode. 

## Model Performance
The metric of interest in this project is **MAPE**(mean average percentage error). The best model has the lowest MAPE.
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/model_results_1.png)
From the image above, we can see that, comparitively, the Facebook prophet model performed significantly worse. 
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/model_results_2.png)
The image below provides a clearer visual comparison between the models by excluding the Prophet model as an outlier. Overall, the **single layer GRU** model performed the best with a MAPE of **0.024**.

|   	|            model 	| VAL_Mape 	|
|--:	|-----------------:	|---------:	|
|   	|       Single_GRU 	|    0.024 	|
|   	|      Single_LSTM 	|    0.030 	|
|   	|              CNN 	|    0.041 	|
|   	|         Deep_GRU 	|    0.055 	|
|   	|        Deep_LSTM 	|    0.056 	|
|   	|          SARIMAX 	|    0.086 	|
|   	| Facebook_Prophet 	|    1.493 	|

## Conclusion
When applying our best model to the business quesion, the best zipcode to invest in within Nevada is **89060** i.e. **Pahrump, NV**
<br><br>
![image](https://github.com/AbsIbs/nevada_time_series/raw/main/images/conclusion.png)
