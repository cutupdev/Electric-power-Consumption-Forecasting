# energy-comsumption-prediction
Group members: Geoffrey Hung, Jiaqi Chen, Wendeng Hu

## Table of Contents
* Introduction
* Data Prepocessing
* Feature Engineering
* Modeling and Evaluation


## Introduction
Modern building consume energy every day. Recently much investments aimed to improve building efficiencies to reduce costs and emissions have been implemented. The question is, How does these energy consumptions related to the environment, and is the improvement working? Our team focus on building models to depict the general patterns of different buildings' energy consumptions and assess the value of energy efficiency improvements by forcasting the future energy consumptions. With better estimates of these energy-saving investments, large scale investors and financial institutions will be more inclined to invest in this area to enable progress in building efficiencies.

The data is downloaded from kaggle [Great Energy Predictor III](https://www.kaggle.com/c/ashrae-energy-prediction/overview), which contains detailed energy usage information of over 1000 buildings over 3 years time. There are overall 20+ features including building geo locations, weather informations, meter consumptions... The train dataset has 20216100 observations (in year 2016) and test dataset has 41697600 observations (in year 2017 and 2018). Those information come in 5 seperate csv files.

Because the datasets are very large, we save it in S3 in AWS. Here provides the link [storage of data](https://s3.console.aws.amazon.com/s3/buckets/mllabchh/?region=us-west-1&tab=overview)

## Data Prepocessing
   - [First look](https://github.com/JiaqiCChen123/energy-comsumption-prediction/blob/master/First_look.ipynb)

Firstly we take a general look into the raw data, and we find that there are **missing values** upon several feature about weather information. 
As for the meter_reading, we find nearly **1/10 of the whole observation has zero values**, which is suspectable.

 - [Data_visualization1](https://github.com/JiaqiCChen123/energy-comsumption-prediction/blob/master/VIsualization%20and%20prepoccessing%201.ipynb)
 - [Data_visualization2](https://github.com/JiaqiCChen123/energy-comsumption-prediction/blob/master/VIsualization%20and%20prepoccessing%202.ipynb)
In this plot, we observe the general meter_reading pattern of different building by site_ids. We find that the pattern of differnt site is differnt, which indicate that site_id is a very important factor.
 - [Data_visualization3](https://github.com/JiaqiCChen123/energy-comsumption-prediction/blob/master/VIsualization%20and%20prepoccessing%203.ipynb)
 Because the limit of .ipynb file is 25 MB, we can not upload the whole notebook, so we only plot one zero meter reading picture. From the picture we can see that the meter_reading has weekend pattern, seasonal pattern and site patterns.
 
 ## Feature Engineering
  - [Data Processing and Feature Engineering](https://github.com/JiaqiCChen123/energy-comsumption-prediction/blob/master/FE.ipynb)
  Previously, when we did data visualization, we already finish some feature engineering. Here, we further implement some feature engineering towards the whole dataset (such as missing value imputation and outlier detection.)
 
## Modeling and Evaluation
- [modeling](https://github.com/JiaqiCChen123/energy-comsumption-prediction/blob/master/model.ipynb)
In this part, we conclude what we have done (data perpossessing and feature engineering); after that, we basically introduce two methods. One is linear regression and another one is Random Forest. We use RMSE to measure model performance.
As is seen, the tree based model berforms better here.



