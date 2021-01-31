# **Python-API-Challenge: WeatherPy**

## Overview

### WeatherPy

The WeatherPy Python script can be used to visualize weather statistics for over 500 cities in the world based on random Latitude and Longitude  coordinate pairs. The script utilizes the citipy Python library to find the city name based on the random coordinates, then performs successive calls on the OpenWeatherMapAPI for each of the cities. The data is then stored in a data frame in order to plot the relationships between each of the weather statistics and the ditance from the equator (Latitude).

### VacationPy
The VacationPy uses the city and weather data from the WeatherPy script in order to plan your next vacation. The script utilizes the jupyter-gmaps functionality anf the Google PLaces API in order to visualy represent the weather data on a map. In order to plan your vacaiton, you need to narrow down the large data frame from the WeatherPy script based on your specific weather preferences. The script is based on my preferences and will need to be adjusted for individual use. Lets get planning!

## File Structure

The **Weayherpy** folder has the following structure:

- WeatherPy
    - WeatherPy.ipynb
    - VacationPy.ipynb
    - api_keys.py
    - .gitignore

### Important

Keep in mind that the api_keys.py file is included in the .gitignore for security purposes. The pi_keys.py file contains the API keys for the OpenWeatherMap API and the Google API with the format below.

#OpenWeatherMap API Key
weather_api_key ='INSERT OPENWEATHERMAP API KEY HERE!'

#Google API Key
g_key ='INSERT GOOGLE API KEY HERE!'

In order to use both the WeatherPy.ipynb and the VacationPy.ipynb, you must first request and activate your own API keys for OpenWeatherMAp and Google Maps.

## Running the Script

1. Verify that the folder and file structure being used on your local directory matches that of the outlined file structure.

2. Open local machine Terminal/GitBash

3. Ensure that citipy and gmaps have been installed for python using the commands below: 
    - pip install gmaps
    - pip install citypy
    
4. Navigate to the appropriate **WeatherPy** directory where all of the folders and files are stored. 

5. Input the **jupyter notebook** command and execute in order to bring up the jupyter notebook online computational tool.

6. Run the WeatherPy script first to generate the list of random cities as well as the weather data for each city. 

7. Lastsly, run the VacationPy script to create the humidity heatmap, filter down the weather results based on specific conditions and then find the hotel/loging closest to the coordinates for each city.  

## Output and Observations

### WeatherPy
#### Weather Data Scatter Plots

The first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
    - The Max Temperature vs. City Latitude scatter plot visualy displays how the latitude of a city impacts its Maximum Temerature. Based on this relationship, it is clear that the highest Maximum Temperatures occur in cities closest to the equator (0 Degreese Latitude).

* Humidity (%) vs. Latitude
    - The Humidity vs. City Latitude scatter plot visualy displays how the latitude of a city impacts its Humidity level. There does not appear to be an obvious trend between the two variables.

* Cloudiness (%) vs. Latitude
    - The Cloudiness vs. City Latitude scatter plot visualy displays how the latitude of a city impacts its Cloudiness level. There does not appear to be an obvious trend between the two variables.

* Wind Speed (mph) vs. Latitude
    - The Wind Speed vs. City Latitude scatter plot visualy displays how the latitude of a city impacts its Wind Speed. There does not appear to be an obvious trend between the two variables.
After each plot, add a sentence or two explaining what the code is analyzing.

The second requirement is to run linear regression on each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

#### Liner Regressions by Hemisphere

A linear regression was performed on the following after splitting the weather data frame into Northern (Latitude >0) and Southern (Latitude < 0) Hemispheres:

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude

    - Based on the Max Temperature vs. Latitude regression for the Northern and Southern Hemispheres, the expected temperatures at the equator are 306.11 K and 299.46 K respectively. Combining these two results together, the Max Temperature near the equator is likely close to 302.78 K.
    - The Northern Hemisphere plot shows that Max Temperature has an inverse relationship with Latitude. As a cities latitude becomes more positive, farther north from the equator, the Max Temperature decreases. 
    - The Southern Hemisphere Max Temperature vs. Latitude regression shows a positive correlation between Max Temperature and Latitude. As Latitude becomes less negative, closer to the equator, Max Temperature increases. 

* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude

    - Based on the Humidity vs. Latitude regression for the Northern and Southern Hemispheres, there does not appear to be a strong relationship between the two variables for either hemisphere. Theoretically, humidity is a function of the air temperature and the the moisture available to be absorbed.

* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude

    - Based on the Cloudiness vs. Latitude regression for the Northern and Southern Hemispheres, there does not appear to be a strong correlation between the two variables for either hemisphere. 

* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

    - Based on the Wind Speed vs. Latitude regression for the Northern and Southern Hemispheres, there does not appear to be a strong correlation between the two variables for either hemisphere.

#### Output Files

- CSV
    - cities.csv
- PNG
    - Cloudiness_Lat_Scatter.png
    - MaxTemp_Lat_Scatter.png    
    - WindSpeed_Lat_Scatter.png
    - Humidity_Lat_Scatter.png
    - Norther_MaxTemp_Lat_Reg.png
    - Southern_MaxTemp_Lat_Reg.png
    - Northern_Cloudiness_Lat_Reg.png
    - Southern_Cloudiness_Lat_Reg.png
    - Northern_Humidity_Lat_Reg.png
    - Southern_Humidity_Lat_Reg.png
    - Northern_WindSpeed_Lat_Reg.png
    - Southern_WindSpeed_Lat_Reg.png

### VacationPy

#### Humidit Heatmap

Heat map  displays the humidity for every city from WeatherPy.

#### Ideal Weather Conditions

Narrow down the weather DataFrame to find ideal weather condition.
    - 75 < Max Temperature < 80 Farenheit, which is ~297 to 300 K
    - Wind Speed < 2
    - Humidity < 90
    - Cloudiness < 30

Droping any rows that don't contain all three conditions. You want to be sure the weather is ideal.

#### Hotel Location Map

Using Google Places API, find the first hotel for each city located within 5000 meters of the coordinates for the cities within the ideal weather conditions list.

The hotels are then plotted on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

#### Output Files

- PNG
    - Humidity_Heat_Map
    - Hotel_Marker_Heat_Map

