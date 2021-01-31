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

## Output

### WeatherPy
The first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, add a sentence or two explaining what the code is analyzing.

The second requirement is to run linear regression on each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, take the time to explain what the linear regression is modeling. For example, describe any relationships you notice and any other analysis you may have.

Your final notebook must:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

#### Observations and Insights

### VacationPy
* Create a heat map that displays the humidity for every city from Part I.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.

  * **Note:** Feel free to adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)

As final considerations:

* You must complete your analysis using a Jupyter notebook.
* You must use the Matplotlib or Pandas plotting libraries.
* For Part I, you must include a written description of three observable trends based on the data.
* For Part II, you must include a screenshot of the heatmap you create and include it in your submission.
* You must use proper labeling of your plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
* For max intensity in the heat map, try setting it to the highest humidity found in the data set.

#### Observations and Insights

