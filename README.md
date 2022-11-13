## Ford GoBike:201902-fordgobike-tripdata
 
## by MBOCK Georges Christian


## Description of the dataset


201902-fordgobike-tripdata is a dataset of the Ford GoBike System [click here](https://github.com/BetaNYC/Bike-Share-Data-Best-Practices/wiki/Bike-Share-Data-Systems.).
This dataset includes information on one hundred and eighty-three thousand four hundred and twelve(183412) individual trips taken in a bike sharing system covering the greater San Francisco Bay Area.
Thus, this information is organized in sixteen(16) columns among others:

'duration_sec': trip duration (in seconds)

start_time', ('end_time'): start (end) date of the trip (YY-MM-DD h:mm:s.t)

start_station_id', ('end_station_id'): identification number of the place where the trip started, (ended)

start_station_name', ('end_station_name'): name of the place where the journey starts (ends)

start_station_latitude', 'start_station_longitude', 'end_station_latitude', 'end_station_longitude': coordinates of the start and end locations of the trip

bike_id': bike registration number

user_type': type of user (subscriber or customer)

member_birth_year', ('member_gender'): year of birth of the user, (gender of the user)

bike_share_for_all_trip': type of bike (Mountain bike or not)

## Summary of findings


**In the evaluation of the data**
I found several problems among others:
* The problems with the order I solved by breaking the variable 'start_time' into 'day' and 'time'and then removing other variables like 'start_station_name' and 'end_station_name' that we felt were not relevant. However, I added the variable 'start_Week' that I thought was relevant to know at what time of the month in terms of week the trips started the most.

* The bad formatting of the types of certain variables that I transformed back into real type for example the variable 'member_birth_year' which was transformed from simple float into categorical variable.
- Missing data: I just deleted the rows with missing values for the variable 'start_station_name' and I separated from the main dataset the rows with missing values for the variable 'member_gender' which I explored afterwards.

**In the exploration**:
* I reshuffled some exceptional values of trip duration, which motivated me to organize the variable 'duration_sec' into different types of trips according to their duration. Among other types, we have: For users with a known member_gender value  
type_1 --->At most 20 minutes;
type_2 --->From 21 to 40 minutes;
type_3 --->From 41 to 1 hour;
type_4 --->From 1 hour to 2.5 hours;
type_5 --->From 2.5 hours to 7 hours;
type_6 --->More than 7 hours

And for the users whose 'member_gender' value is not known we have the following different routes:
type_1 --->At most 20minutes;
type_2 --->From 21 to 40minutes;
type_3 --->From 41 to 1 hour;
type_4 --->From 1 hour to 2.5 hours;
type_5 --->From 2.5hours to 5.5hours;
type_6 ---> More than 5.5 hours

* For users whose gender is known, I noticed that the fact that a user is a Subscriber or Customer is not directly influenced by his gender, nor by the time of the month in terms of week or the time of the day in terms of hours during which he makes his trip. Nevertheless, I noticed a weak influence of the type of trip on whether a user is a Subscriber or a Customer. Moreover, this influence seems to create more of an influence of gender on whether a user is a Subscriber or a Customer when it is known that the user makes the type_5 trip. I also noticed that no Customer type users use the all-trip type bikes.

* For users whose gender is unknown, I noticed that whether they are a Subscriber or a Customer seems to be directly influenced by the type of trip. 


## Main ideas for the presentation

For this presentation, I start by giving the absolute frequency distribution of user type, then focus on different relationships possibly between my variable of interest 'user_type' and other variables like: 'duration_sec' Vs 'type_trip', 'member_gender' Vs 'user_type', 'type_trip' Vs 'user_type' and 'bike_share_for_all_trip' Vs 'user_type' and then multivariate relationships like : 'Type_trajet' = 'Type5'|'user_type' Vs 'menber_gender', and finally 'member_gender'=('Female' or 'Male' or 'Other')|'user_type' Vs 'bike_share_for_all_trip' and to finish I present the influence of the type of trip on the type of user of unknown gender 'user_type' Vs 'type_trip'.









