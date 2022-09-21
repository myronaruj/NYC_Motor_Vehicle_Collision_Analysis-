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
