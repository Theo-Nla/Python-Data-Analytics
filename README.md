# Global YouTube Data Analysis

## About
YouTube is a vast and diverse video-sharing platform that engage it users with video contents, it has revolutionized the way we consume and share information, entertainment and ideas. There are three kinds of users who engage themselves with YouTube: Video content creators, Video content lovers and Digital marketers who use YouTube advertising service to publicize their product and service information.

## Purposes and Objective Of the Project
This project aims to explore the YouTube landscape to understand top performing branches and products, performance trend of different service providers, customer behavior.

## About Data
The dataset Global YouTube Statistics 2023 was obtained from Kaggle and this dataset contains engagement information on the most subscribed YouTube channels. The data contains 28 columns and 1000 rows:
rank, Youtuber, subscribers, video views, category, Title, uploads, Country, Abbreviation, channel_type, video_views_rank, country_rank, channel_type_rank, video_views_for_the_last_30_days, lowest_monthly_earnings, highest_monthly_earnings, lowest_yearly_earnings, highest_yearly_earnings, subscribers_for_last_30_days, created_year, created_month, created_date, Gross tertiary education enrollment (%), Population, Unemployment rate, Urban_population, Latitude, Longitude

## Data Wrangling

1. Checking for missing values

2. Missing values were replaced by.
•	Dropping the last six columns as they will not be used for this analysis
•	Replacing missing values with not available
•	Replace missing value with the mode
•	Dropping remaining missing values

3. Changed the “created_date” column data type to date time

## Exploring the Data

  ## Statistical Analysis
## 1.	Univariate Analysis
This analysis aims to analyze the
1.	Category with the most activity
2.	Country with the highest amount of YouTube activities
3.	Distribution of content creators by continent
4.	Measures of central tendency (Mean, Median and Mode) 
5.	Distribution of
•	Subscribers: The channels with the most subscribers have fewer density
•	Uploads: Fewer number of channels make more uploads
•	Highest Yearly Earnings: the more the earnings the fewer the number of people making more earnings


## 2.	Bivariate Analysis
This analysis aims to answer the between two categories of product. 
•	Relationship between Uploads and subscribers
•	Relationship between Uploads and Highest_yearly_earnings
•	Relationship between Highest_yearly_earnings and Subscribers
•	Using correlation matrix to check how variables are related
•	Using heat map to check for correlation

## 3.	Multivariate Analysis
•	This analysis aims to uncover the relationship subscribers and yearly earnings in different countries

## Feature Engineering
A new column was created from country column to create the continent column using the “if conditional statement and Lambda”.

    -	Creating the function to fill the continent column with the appropriate continent of the country. 

def result(Country):
    if Country in Africa: return 'Africa'
    elif Country in Europe: return 'Europe'
    elif Country in Oceania: return 'Oceania'
    elif Country in South_America: return 'South_America'
    elif Country in North_America: return 'North_America'
    elif Country in Asia: return 'Asia'

    -	Adding the function into the dataframe
df_clean['Continent'] = df_clean.Country.apply(lambda x:result(x))
 
