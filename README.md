# Case Study: How can Cyclistic gain more subscribers?

## Used Software
- Python
- Jupyter Notebook
  - pandas
  - matplotlib
  - pathlib

## Problems
- There is a separate dataset for each quarter.
- CSV has too much data for Excel to handle.
- The data don’t align across the quarterly reports (Headers are different).
- Outliers for trip duration skew the data.

## Solutions
- Use python to combine all of the files, prepare the data, and analyze the data.
- Filter out the outliers using Python.

## Scenerio
This is a fictional scenario where I am working as a Junior Data Analyst for a fictional company, Cyclistic. It is currently the first quarter of 2020.

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown
to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations
across Chicago. The bikes can be unlocked from one station and returned to any other station
in the system anytime.

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to
broad consumer segments. One approach that helped make these things possible was the
flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships.
customers who purchase single-ride or full-day passes are referred to as non-subscribers.
customers who purchase annual memberships are Cyclistic subscribers.

Cyclistic’s finance analysts have concluded that annual subscribers are much more profitable
than casual riders. Although the pricing flexibility helps Cyclistic attract more Non-Subscribers, our manager believes that maximizing the number of annual subscribers will be key to future growth.
Rather than creating a marketing campaign that targets all-new Non-Subscribers, our manager believes there is a solid opportunity to convert casual riders into subscribers. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.

Our manager has set a clear goal: Design marketing strategies aimed at converting cnon-subscribers into annual subscribers. In order to do that, however, the team needs to better understand how annual subscribers and non-subscribers differ, why non-subscribers would buy a membership, and how digital media could affect their marketing tactics. Our manager and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

## Introduction

I have been tasked with figuring out how annual subscribers and non-subscribers use Cyclistic bikes differently.

Based on the scenario, we can assume annual subscribers for Cyclistic are more profitable than single-ride or full-day riders (referred to as non-subscribers).

Since this is a fictional scenario we will analyze the last year of data since it is the most recent and therefore most representitive of the customers.

Thus, the business question we are looking to answer is:
Over the past year, are there any differences in riding patterns between Subscribers and Non-Subscribers?

## Preparation

To prepare, I downloaded data that has been made available by Motivate International Inc. under this [license](https://www.divvybikes.com/data-license-agreement) to conduct this case study. The data was separated out by quarter, so I downloaded 4 reports. 

The data has too many lines for Excel to handle, so I wrote a Python code using Jupyter Notebook to read in each quarter of Cyclistic data. Using the pandas Python library, I explore the data.

After looking at each quarter’s data, I found that the headers were different from the rest, so I renamed them to match after confirming the columns were the same. I wrote a code to combine all quarter’s data into one csv to analyze the data as a whole.

To continue preparing the data, I check the data types, and convert each column to the correct data type. I check the data for duplicates – in this case there were none, and fill null values. I converted the trip duration from seconds to minutes since minutes are understood easier.

To finish preparing the data, I added a column for date, month, and day from the start_date column since I want to analyze based on those criteria. I filter to just the columns we will need and then we are ready to start analyzing.

After beginning to analyze, I realize that there are outliers in the data that skew the data, and filter these out and run the Python script to analyze again.

## Analyze

I start the analysis by getting an understanding of the data by checking the proportion of the riders in the last year that are subscribers. It appears a large proportion of riders in the last year are subscribers, 77% to be exact, leaving just 23% that are not members. I then check out the demographic of these subscribers/non subscribers and found out subscribers seem to slightly have more men than non-subscribers as shown below. Though, deeper analysis may be required to prove this, since there is such a small difference.

| Gender | User Type | Proportion |
| ----------- | ----------- | ----------- |
| Female | Subscribers | 85% |
| Female | Non-subscribers | 15% |
| Male | Subscribers | 91% |
| Male | Non-subscribers | 9% |

I want to also look at the trip duration across user types since that is the only piece of quantitative data provided. The info I produced from the data is shown below:

| User Type | Mean |
| ----------- | ----------- |
| Subscribers | 11.08 |
| Non-subscribers | 28.85 |

Right away, I notice there is a clear difference between the mean trip duration between subscribers and Non-Subscribers. It seems, on average, non-subscribers trip duration is approximately 62% longer.

I also compared the amount of riders per month, and there were no clear differences in trip patterns between subscribers and non-subscribers. However, we were able to discover that there are more trips in the third quarter and the most trips in July.

Similarly, I compared subscribers and non-subscribers based on the number of rides by the day of the week to see if there is a difference in riding patterns. This time, it showed an inverse-like pattern. For subscribers, it seems like trips are taken more during the weekdays (Sun-Thu) while non-subscribers seem to take more trips on the weekends (Fri-Sat).

## Share
(When sharing data, I try to keep it, short, simple, and to the point)

**Objective**

I am looking to determine if there are any differences between subscibers and non-subscribers for Cyclistic's customer base.

**Day Of Week**

It seems non-subscribers take trips more during the weekends (Fri-Sat) while subscribers take more trips during the weekdays (Sun-Thu).
![Trips By Day](/images/trips_by_day.png)

*Data in the graph is from 2019*

*0 = Sunday, 1 = Monday, 2 = Tuesday, 3 = Wednesday, 4 = Thursday, 5 = Friday, 6 = Saturday*

This makes sense because usually, people have more free time weekends since they do not work. Thus they have more time to take longer, more enjoyable rides rides.

**Trip Duration**

This shows in the data since throughout the year, it seems the average trip duration for non-subscribers is higher than non-subscribers. In fact, overall, non-subscribers' average trip duration is 62% greater than subscribers.

![Daily Average Trip Duration](/images/daily_avg_trip_duration.png)

*Data in the graph is from 2019*

## Conclusions
1. Non-subscribers trend shows they take more trips on weekends (Fri-Sat) than weekdays (Sun-Thu) while subscribers take less trips on weekends than weekdays.
2. On average, non-subscibers' trip durations are 62% longer than subscribers' trips.

## Recommendations
- Add incentives in the Cyclistic subscription for longer rides.
- Add incentives in the Cyclistic subscription for weekend rides.

