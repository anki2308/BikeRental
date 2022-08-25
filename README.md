# BikeRental
Bike sharing systems are a means of renting bicycles where the process of obtaining membership, rental, and bike return is automated via a network throughout the city.

# Data description

There are two files in one is hourly basis and the other is daily basis and the only difference between them is the hour attribute which is absent in day file. The one with hourly basis has 17379 bike rental details and daily basis has 731 biking details. So, for EDA part we got the indights from both file but for the model building we carried out with hour file.

The business meaning of each column in the data is as below:

season: The current season (1:winter, 2:spring, 3:summer, 4:fall)
yr: year (0: 2011, 1:2012)
mnth: month ( 1 to 12)
hr: hour of the day (0 to 23)
holiday: weather day is holiday or not
weekday: day of the week
workingday: if day is neither weekend nor holiday is 1, otherwise is 0
weathersit: The Weather forecast for the day
1: Clear, Few clouds, Partly cloudy, Partly cloudy
2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
temp: Normalized temperature in Celsius.
atemp: Normalized feeling temperature in Celsius.
hum: Normalized humidity. The values are divided to 100 (max)
windspeed: Normalized wind speed. The values are divided to 67 (max)
casual: count of casual users
registered: count of registered users
cnt: count of total rental bikes including both casual and registered

Created a ML model which predicted the number of bikes which will be rented at a given hour of the day
Target Variable: cnt
Predictors: holiday, weather, registered users etc.

# EDA and Insights:

![bikecnt](https://user-images.githubusercontent.com/101788326/186696068-9b53355d-15df-413d-ab5a-050113891882.jpg)


- Total number of Bike Renters: 3292679 
- Total number of registered User: 2672662 
- Registered User who actually Rented Bikes 81.17 % 
- Total number of Non-Registered User: 620017 
- Non-Registered User who actually Rented Bikes: 18.83 % 
- Bike Rental per hour: 189 • Bike Rental per minute: 3 
- There are all numerical variable only the date time is object type. 
- There is high positive correlation between temperature and actual feel of temperature and also a positive correlation between Registered User and Count of bikes.

# Data Preprocessing:

- Outliers: Outliers bias the training of machine learning models. As the algorithm tries to fit the extreme value, it goes away from majority of the data.
We treated the outliers for humidity and windspeed. Others we didn't treat because it has distinct values and if we have handled this may give wrong interpretation to our model and prediction may go wrong.

- There were no missing values.

- We then standardized the data.

# Model Building and Evaluation:

![bb](https://user-images.githubusercontent.com/101788326/186699038-75d7803f-922f-4132-8ef5-44cf91001aed.jpg)




