# Time-Series-Forecasting-using-Walmart-Dataset

## Project Description

Time has been an important factor ever since we first started collecting data. A specific method of studying a collection of data points over a period is called a time series analysis. Organizations can fully comprehend the underlying causes of long-term trends or systemic patterns by applying time series analysis. When they examine data at regular intervals, they can use time series forecasting to estimate the probability of future events and it is also used to highlight likely variations in the data, such as seasonality or cyclical activity, which enhances forecasting by enabling a better understanding of the data variables. 

####  About Walmart Dataset
To accomplish this, we have chosen the Walmart dataset, which contains data on 45 stores’ weekly sales for the years 2010–2012. This dataset also includes information on factors that affect sales, such as holidays, weather, fuel prices, CPI, and unemployment. By performing a predictive analysis on the Walmart dataset, we can better comprehend the data and trends, which in turn allows us to forecast future events.

As of July 31, 2022, Walmart has 10,585 stores and clubs in 24 countries operating under 46 different names. Among them, 45 stores were picked up for fundamental analysis. According to the May 2022 Fortune Global 500 list, Walmart is the world's top-grossing company with annual sales of approximately $570 billion.

* The Walmart dataset we are using consists of 8 columns and 6,436 rows.
* Each of the columns represents different sales aspects of the Walmart dataset.

The 8 columns of the Walmart dataset are explained briefly: 

* Store numbers: Since we have considered a dataset of 45 stores, we now use the dataset from 45 stores to be the total number of stores.
* Date: It is the week of sales; it is in the format of dd-mm-yyyy.
* Weekly sales: the sales of the entire store in a week.
* Holiday flag: We consider the holidays for each week, if it is a holiday, then it is represented by a 1, if not then it is represented as a 0.
* Temperature: Average temperature of the week of sales.
* Fuel price: Fuel price in the region of the store
* CPI: Customer price index
* Unemployment: An unemployment rate of that specific store in that specific region 

___________________________________________________________________________________________________________________________________

## Actionable decision(s) that we can anticipate from our project

We will be analyzing the sales trends of the Walmart dataset and will address the below questions:

* Which stores have the maximum weekly sales?
* Among the 45 stores, in Which store do the sales vary a lot?
* Which stores have the maximum quarterly growth rate (Q3’2012)?
* Which stores have the highest sales fluctuation over the considered period?
* Which holiday week has the highest negative impact on sales?
* Which quarter has the highest and lowest unemployment rate?
_________________________________________________________________________________________________________________________________________

## Proposed Job pipeline flow

The CRISP-DM steps are popularly known as the cross-industry standard process for data mining. It is one type of process model that acts as a base for any data science process. There are six sequential phases namely:

### Business Understanding

The first phase is about understanding the project requirements and objectives from a business perspective. In our project, we identified the business problem (sales churn), evaluated the situation, and then determined the questions we wanted to address after conducting the data analysis. The Problem statement here is about Walmart sales forecasting and predictions using time series analysis.

### Data Understanding

The second step is data understanding where any quality issues pertaining to the data are identified. It is also the phase in which an analyst goes on to find interesting subsets to form hypotheses for hidden information. Here, we have chosen the appropriate dataset relevant to sales forecasting. The dataset also includes information on factors that affect sales, such as holidays, weather, fuel prices, CPI, and unemployment. 

