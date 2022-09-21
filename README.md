# NYC_Motor_Vehicle_Collision_Analysis

NYC Motor Vehicle Collision Analysis – A Data Warehouse and Business Intelligence Project


**Introduction**

New York city is the city of dreams but in this dream city, many accidents occur daily. Road safety is a 
critical issue to every person and it’s the important part of their daily lives. Although some collisions are 
inevitable, but many can be saved with some analysis. That’s why, it is quite important to analyze 
vehicle collision history in New York City which will help in preventing these accidents in future.
The Motor Vehicle Collisions data tables contain information from all police reported motor vehicle 
collisions in NYC. The police report (MV104-AN) is required to be filled out for collisions where someone 
is injured or killed, or where there is at least $1000 worth of damage 
(https://www.nhtsa.gov/sites/nhtsa.dot.gov/files/documents/ny_overlay_mv-104an_rev05_2004.pdf). 
It should be noted that the data is preliminary and subject to change when the MV-104AN forms are 
amended based on revised crash details.

**Data sources**

The data sources have been taken from the NYC Open Data site and is focused on the motor vehicle 
collisions that have occurred in the city. It consists of three large datasets comprising of the crashes, 
person, and vehicles data which can be downloaded from the data sources in any format we require. It 
contains large amount of data ranging over a span of 2016 to 2019 over 4 million records and gets 
updated daily on website.
For weather data we have from the virtual crossing data site which returns data from the specific date 
entered and zip code. We plan to extract the weather data from here according to the requirements and load it.

Motor Vehicle Collisions – Crashes: It contains details on the crash event Each row represents a crash event. 
Motor Vehicle Collisions – Vehicles: It contains details on each vehicle involved in the crash. Each row 
represents a motor vehicle involved in a crash. 
Motor Vehicle Collisions – Person: It contains details for people involved in the crash. 

Each row represents a person (driver, occupant, pedestrian, bicyclist) involved in a crash.
Weather Data- It contains data from New York city which is based on zip code. We can find the 
temperature and weather details from the file. We will join this weather data with the zipcode 
information in Crashes file and will later help us make assumptions on crashes based on weather 
conditions. 

The data was extracted from visual crossing 
Links: https://data.cityofnewyork.us/browse?Data-Collection_DataCollection=Motor+Vehicle+Collisions&limitTo=datasets&sortBy=most_accessed&utf8=%E2%9C%93
https://www.visualcrossing.com/weather/weather-data-services/10466/metric/last15days



![image](https://user-images.githubusercontent.com/29515861/191560281-62d00d9e-a44b-4f03-b4f5-de2149e5fab9.png)


**Project Flow**

The data is available in formats such CSV, Excel, JSON, XML etc. Primarily we are considering importing 
form CSV file. In order to facilitate incremental data loading, we will divide the csv file in parts then 
upload chronologically. We will be implementing different types of SCDs based on data requirements. 
We are planning to import data using the SSIS package into the database. We will do the required 
preprocessing like joining tables and eliminating columnar discrepancies and then store the cleaned data 
in staging. We are also planning to maintain audit logs which will check for anomalies in data like zip 
code in wrong format, null values, invalid formats. We will be creating the dim and the fact tables based 
of the data sources. We will also be loading incremental data on monthly or quarterly basis and 
implementing SCD along with error handling. Also, one of our goals would be automating the loading 
activities.

This will show general flow of the complete project.

![image](https://user-images.githubusercontent.com/29515861/191560522-7f93f161-471d-4243-b24e-a7c686814278.png)

**Data Model**

Dimension modelling showing the relationship between the dim and fact tables.

![data model](https://user-images.githubusercontent.com/29515861/191560761-59013b19-be1b-4fbd-8477-b1c0df8bd232.jpg)


**Description**

We have created a star schema with 7 dimension tables as shown in the above image with one fact table 
in the center. The 7 dimension tables and fact tables are:
1. dimCrash
2. dimDate
3. dimDriver
4. dimLocation
5. dimPerson
6. dimVehicle
7. dimWeather

factAccident is the fact table.

**Data Flow**

![ssis package](https://user-images.githubusercontent.com/29515861/191561131-131374c6-077b-41cd-9035-cddfdf74af88.png)


**Visualizations and Insights**

![image](https://user-images.githubusercontent.com/29515861/191564254-dcc8eae2-a258-4e8d-b78e-72d9d6f96b36.png)

![image](https://user-images.githubusercontent.com/29515861/191564369-d8aa8900-a399-4456-adf7-392bb5d69a93.png)

![image](https://user-images.githubusercontent.com/29515861/191564533-ff5c73a8-386d-49e4-982a-e35f8e42a613.png)

![image](https://user-images.githubusercontent.com/29515861/191564620-a9dea17d-53d3-4ae1-833d-db2b9434a5c3.png)

![image](https://user-images.githubusercontent.com/29515861/191564751-75c31600-efee-4071-9c35-b3559b96cc06.png)

![image](https://user-images.githubusercontent.com/29515861/191564825-a95dbc91-509f-4baa-a6d0-39b299c3916b.png)


**Insights**

Majority of accidents occurred when number of occupant was one.
Highest number of accidents with the greatest number of affected occupants happened in sedan and station wagon.
Pedestrian/bicyclist confusion was the most contributing factor.
Total fatality trend seems to be decreasing from Jan 2016 to Jan 2020.





