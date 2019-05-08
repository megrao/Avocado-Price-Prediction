## Avocado Price Prediction

### Abstract
Renowned statistician and management guru late W. Edwards Deming rightly said - "If you do not know how to ask the right question, you discover nothing." Therefore, it is essential to define the problem and carefully interrogate the data with the right questions, before proceeding to perform the necessary pre-processing of the sample as per the research design. Following are the details of the project undertaken.
Topic: Analysis and Prediction of Avocado prices (specifically Hass Avocados)
Industry: Retail 
Data: The dataset comprises of attributes such as the Average sales price per unit, Date of observation, Total volume, Total bags and volume breakup for each bag size and product code of Hass avocados. Here is the link to the dataset homepage - http://www.hassavocadoboard.com/retail/volume-and-price-data and https://www.kaggle.com/neuromusic/avocado-prices.
### Problem Statement: Find the following insights from the data: 
	Effect of avocado type (conventional or organic) on pricing. Furthermore, explore if we can reverse engineer and build a model to predict the type of avocado in front of us, based on price.
	Understand the price fluctuation across different regions. Where was the maximum price?
	Study the price distribution and fluctuation in the past few years. Find the most expensive year.
	Predict and forecast of future prices. Will it increase or decrease?

### Acknowledgement
First and foremost, many thanks to Hass Avocado board for the dataset and author Brain Godsey for his book ‘Think Like a Data Scientist: Tackle the data science process step-by-step’. I express my gratitude towards my professor Dr. Glen Mules for the useful links, encouragement and guidance. Furthermore, I thank all the publishers of useful links and codes online.

### Brief Overview 

	First things first. What is a Hass Avocado?
A delicious variant of avocado, also known as Bilse avocado, with dark green-colored, bumpy skin. 
	Why this topic?
Predictive analytics was routinely performed during my undergraduate study in Bioinformatics engineering. At work, we used to generate reports to enable users to analyze and predict fuel and commodity prices. Hence the interest.
	Why is subject matter important?
I consider Avocado price as a unit of study. Price analysis and prediction can be done with any product or commodities irrespective of field. The questions we ask may slightly differ, but the basic process remains the same. Hence, it has countless applications that makes it important. On a lighter note, Avocados are tasty and nutritious, and worthy of study.
	What are you hoping to achieve?  
Reiterating the problem statement, the goal is to unearth valuable insights from the data. Below are some specific goals. 
	Effect of avocado type (conventional or organic) on pricing. Furthermore, explore if we can reverse engineer and build a model to predict the type of avocado in front of us, based on price.
	Understand the price fluctuation across different regions. Where was the maximum price?
	Study the price distribution and fluctuation in the past few years. Find the most expensive year?
	Predict and forecast of future prices. Will it increase or decrease?
Upon completion of this study, I hope to learn how to approach and handle data in the initial step of data preparation.

Dataset Studied

	Source URL: http://www.hassavocadoboard.com/retail/volume-and-price-data and https://www.kaggle.com/neuromusic/avocado-prices
	The dataset comprises of retail volume and price data of conventional and organic Hass avocados in the United States. We are excluding global data from this study. Nevertheless, the Hass Avocado Board website carries several insightful datasets for future research.

### Description & Structure of the Data

	Layout

o	Quoting directly from the data owners, below is an excerpt from the website of Hass Avocado Board describing the data on their website.
The table represents weekly 2018 retail scan data for National retail volume (units) and price. Retail scan data comes directly from retailers’ cash registers based on actual retail sales of Hass avocados. Starting in 2013, the table below reflects an expanded, multi-outlet retail data set. Multi-outlet reporting includes an aggregation of the following channels: grocery, mass, club, drug, dollar and military. The Average Price (of avocados) in the table reflects a per unit (per avocado) cost, even when multiple units (avocados) are sold in bags. The Product Lookup codes (PLU) in the table are only for Hass avocados. Other varieties of avocados (e.g. greenskins) are not included in this table.

o	Domains of attribute values: The columns in the initial and final table table are as follows.
	Date - The date of the observation
	Average Price - the average price of a single avocado
	Total Volume - Total number of avocados sold
	4046 - Total number of avocados with PLU 4046 sold
	4225 - Total number of avocados with PLU 4225 sold
	4770 - Total number of avocados with PLU 4770 sold
	Total Bags – Total number of avocado bags sold 
	Small Bags - Total number of small avocado bags sold
	Large Bags - Total number of large avocado bags sold
	XLarge Bags - Total number of extra-large avocado bags sold

Consolidated table from Kaggle.com has the following additional entries.
	Unnamed field: probably meant with Index number
	Year: Year of sale
	Region: Region of sale
	Type: Specifies if it is Conventional or Organic Avocado

### Notes on Exploration of the dataset

	There are 14 columns and 18,249 entries in the consolidated ‘Avocado.csv’ file from Kaggle dataset. 
	Dataset has the records from January 2015 to March 2018.
	The initial dataset from Hass Avocado board is in excel format with fewer columns. From visual examination, the additional columns in the consolidated sheet are Type (specifying if conventional or organic), Region and Year. Hence, we can append data in the future by filtering out latest data, adding the aforementioned appending to existing consolidated dataset ‘avocado.csv’.
	A quick study using Tableau software revealed that all regions are well-represented and there is sufficient yearly data.  

#### Explore and document the data and data structures manually 

o	The product lookup codes (PLU) codes were studied. Below are the details.
	4046 – Hass Avocado - small
	4225 – Hass Avocado - large
	4770 – Hass Avocado - Extra Large
o	Index column in the consolidated sheet from Kaggle can be eliminated as there are many inconsistent entries. It is also unnamed in the csv file.
o	As per the python pre-processing (using Jupyter notebook), there are no null value rows in the dataset. 
o	Certain columns do have zero (for example No. of Extra-large bags) but it looks genuine and correct.
o	Certain columns representing number of avocados is in float format which is unlikely to be true as number of items must ideally have integer format.

### Questions to Ask of the Dataset

o	Why was the data collected?
Data was collected for research purpose by Hass Avocado Board. They routinely perform various projections, market analysis and forecast.

o	How was the data collected?
As per their (Hass Avocado board or HAB) website, data is collected from IRI/FreshLook Marketing Multi-Outlet (MULO) retail scans. The reporting reflects retail sales scans across the following channels: grocery, mass, club, drug, dollar and military. HAB's calculation is based in part on data reported by Information Resources, Inc. through its Freshlook Service.

Do we have the required license, credentials or permission to access the data? (Castle, 2018) Yes, it is an open dataset and I verified using the website’s Terms of use section.

o	Is the data reliable and accurate? Is there any missing data?
Again, as per the HAB website, the information was believed to be reliable at the time supplied by IRI even though it is not legally guaranteed. Without limiting the generality of the foregoing, specific data points may vary from other information sources. Generally, it is deemed to be reliable and fairly accurate. There is no missing data as per initial analysis.

o	Is the data up to date? 
Yes, it is updated every four weeks. For the purpose of study, we are using entries from January 2015 to March 2018.

o	Do we have tools and network connections to implement this experiment?
Yes, we do.

o	What is the data format of the datasets? Is there any disparity that requires standardization of data (to convert to a single workable format)?
The consolidated sheet from Kaggle Open dataset is in csv (column separated) format and data from HAB website is in excel format. It is very easy converting between these two formats. Hence no issues.

o	What is the size of the dataset? Do we need to create a subset for granular analysis? (Castle, 2018) Furthermore, Is there data for future study? 
Dataset has 14 columns and 18,249 entries. We have ample data, thanks to the HAB website. There is sufficient data for current as well as future studies. The website itself provides smaller subsets of data that can be easily downloaded and used for any granular analysis. If needed, we can also work on creating a smaller subset using Python, R or SQL.

o	Is there a need to join tables or create a summary table? Can it be done manually or using computational tools?
The HAB website has smaller subsets of data for each year, region and type. Fortunately, we can use the consolidated dataset named ‘avocado.csv’ in Kaggle open dataset. There is no need to manually modify the table. 


o	Do we need more data to perform the current study? Is there a need to merge and consolidate data? Or to download data from outside the organization? (Castle, 2018)
At the expense of sounding redundant, yes, there is sufficient data for current as well as future studies. There are various types of historical data in HAB’s website. However, we are relying on Kaggle’s consolidated dataset as they have painstakingly merged regional information of over 330 entries each, totaling to over 18,000 entries, and generously uploaded in their repository for academic purposes. To perform certain tasks during the research execution phase, we may need to use computational tools (aka python in this case) to segment and segregate the data.

o	Do we have too much data to process? Will it be time-consuming? (Godsey, 2017)
No, we have entries 18,249 entries that can be easily processed without much delay.

o	Is the data accessed or modified in the production environment? Are there business users to be notified? Is there a downtime?
No to all three. We are working with an open dataset downloadable in csv and excel format. Hence, there is no need to notify users or plan a downtime. We are not toying with sensitive data or environment.

o	Any assumption?
For the purpose of this study, we are assuming a single supplier for the avocado stock, in order to avoid undue complications.

o	Are there inconsistent entries or redundant that require cleaning of the data? Can it be cleaned in the current environment with pre-existing tools and software? Is it possible to clean it manually? (Castle, 2018)
Yes, there are couple of minor tweaks, discovered and documented in the data exploration step, to be performed. Even though manual cleaning sounds easy, python is more efficient in handling this task. Hence, we are planning to employ Jupyter notebook for the same.

o	Can the data at hand address our goals?
Yes, we have the necessary data to answer the problems statements / goals and provide business insights.

o	Is the proposed methodology compatible with the data format? Is it efficient?
Yes, data format is compatible, and the methods proposed are efficient.

o	What happens if a test fails? Is there a spot-check? If it shows an error, how do we proceed? (Godsey, 2017)
We are not planning to rely on a single method. There are multiple ways and we can verify solutions from time-to-time using alternate and manual methods. If solution is wrong, we will substitute the main method with the alternate method.

o	What inferences can we make? What truth is revealed or predicted? (questions suggested by Professor Glen Mules)
Whether organic is more expensive compared to conventional Hass Avocados (we know the truth but let’s allow data to verify!). Furthermore, based on the price, experiment if we can build a model to predict the type of avocado in front of us. The average price distribution and yearly fluctuation across regions educates us about the market trends, and the forecast tells us what to expect in the future (whether the prices will increase or decrease in 2019 and 2020). Please refer Jupyter notebook for the complete results. Few screenshots below.

### Insights

Couple of interesting insights from the execution part. 
	As per the forecast, the prices are most likely to drop in the year 2019 and 2020.
	San Francisco had the highest Avocado price in the year 2016. The type was organic Avocados. It comes as no surprise that Organic are pricier but sells in lower volumes.
	Nevertheless, Hartford Springfield had the highest Average Price (followed by San Francisco and New York).
	West region is the highest consumer of Hass Avocados. State of California is the frontrunner among the states in US.
### References

	Castle, E. (2018, August 29). 6-questions-to-ask-when-preparing-data-analysis [Web log post]. Retrieved November 11,2108 from /https://www.sisense.com/blog/
	Godsey, B. (2017). Think Like a Data Scientist: Tackle the Data Science Process Step-By-Step. Manning Publications.
	OpenClipArt-Vectors [Web log post - Animation]. https://pixabay.com/en/avocado-food-green-half-nutrition-161822/
	Tookapic [Web log post - Photograph]. https://pixabay.com/en/photos/avocado/?
	FoodieFactor [Web log post - Photograph]. https://pixabay.com/en/avocado-avocados-food-healthy-food-2644150/
	http://www.hassavocadoboard.com/retail/volume-and-price-data

