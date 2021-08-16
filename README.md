# Google Data Analytics - Cyclistic Bike-Share

### Introduction

As a junior data analyst working with the marketing analyst team at Cyclistic, a bike-share company in Chicago. Cyclistic has nearly 6000 bicycles and over 600+ bike stations within their program. The company has two different types of riders, casual riders and members.

The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. With this focus, your team wants to identify how annual members and casual riders use Cyclistic bikes differently. 

From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

### About the Company

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geo-tracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.

In order to answer this business question, I will use the data analysis process: 
**Ask, Prepare, Process, Analyze, Share, and Act**

## ASK

#### Summary of business task:

* The goal of this case study is to identify how annual members and casual riders use Cyclistic bikes differently.

* By analyzing the data, we can identify trends and draw insights in the customer behavior to help design marketing strategies aimed at converting casual riders into annual members.

#### Consider key stakeholders

* Primary stakeholders: Lily Moreno, Director of Marketing and Cyclistic executive team
* Secondary stakeholders: Cyclistic marketing analytics team

## PREPARE

#### Prepare the data

* The data that we will be using is Cyclistic’s historical trip data from the last 12 months (May-2020 to Apr-2021). The data has been made available by Motivate International Inc. on this link under this license.
* The dataset consist of 12 csv files with 13 columns and more than 4 million rows
* Data bias and credibility: **ROCCC** 
  * **R**eliable - It is complete and accurate and it represents all bike rides taken in the city of Chicago for the selected duration of our analysis
  * **O**riginal (data sets derived from divvy-bike share program), 
  * **C**omprehensive (information (13 variables) required for analysis present), 
  * **C**urrent (yes, updated data available), 
  * **C**ited (yes, here)

## PROCESS

#### Microsoft Excel
 
* Each dataset was transformed where new columns were added based on using formulas on the original data 
* Includes the ride length, ride month, day of the week, time of the day, and ride hour
[See formulas](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/Excel/Data%20Transformation%20(Formulas))
[See screenshot](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/Excel/Picture%20of%20Columns%20Excel%201.JPG)

#### PgAdminV5 (PostgreSQL)

* Since the data files contain thousands of rows and take up a substantial amount of memory, I used PgAdmin v5 via PostgreSQL to inspect, clean, and merge the data for analysis

* For each dataset, a table was made based on the appropriate data type for each column and the corresponding .csv file was imported 

* Once all tables were made, they were merged into a new table using the UNION statement
[See SQL Query](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/SQL/SQL%20Data%20Processing)

#### Data Cleaning

* Check for duplicates
* Check for null values
* Check for negative values
* Check for outliers (IQR Method)

[See SQL Query](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/SQL/SQL%20Data%20Cleaning)

## ANALYZE

#### Descriptive analysis

* Summary Statistics (Ride_Duration) [See SQL Query](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/SQL/SQL%20Analysis%20(Summary%20Statistics))
* Ride_Count Analysis [See SQL Query](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/SQL/SQL%20Analysis%20(Ride%20Count))
* Ride_Duration Analysis [See SQL Query](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/SQL/SQL%20Analysis%20(Ride%20Duration))
* Top start/end stations [See SQL Query](https://github.com/jokonkwo/GDACert-Bikeshare/blob/main/SQL/SQL%20Analysis%20(Station%20Count))

## SHARE

#### Data Visualization - Tableau

* Member vs Casual:
  * Total Ride Count: overall, month to month, weekday, time of day, and ride hour, rider type

***Insert Dashboard link***
  * Avg Ride length: overall, month to month, weekday, time of day, and ride hour

***Insert Dashboard link***
  * Top five stations count by member_casual

***Insert Dashboard link***
## ACT

#### Conclusion

* Difference between member and casual customer trends:
  * time of year (Winter vs Summer)
  * day of the week (weekdays vs weekends)
  * ride hour (8AM, 5PM spikes)
  * time of the day
  * stations used
  * bike type
  * ride duration
 
* Top 3 recommendations:
  * Marketing strategies with discounts at casual trends (weekdays to increase, summer capitalize, work hours vs evenings/late night)
  * Exclusive access to high usage casual bikes (classic vs. docked/electric bikes)
  * Station location/nearby business deals (start + end) for members could work as strategies for subscription conversion
