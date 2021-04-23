What's the Weather Like?

## Background

What we are trying t do is to answer a fundamental question: "What's the weather like as we approach the equator?"


## Part I - WeatherPy

In this example, a Python script has been used to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, the script used [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api) to create a representative model of weather across world cities. Then a a weather check performed on each of the cities using a series of successive API calls which included a print log of each city as it's being processed with the city number and city name. Then the retrived data of cities is saved in a CSV file. 

Then a series of scatter plots created to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

A PNG image saved for each scatter plot.

Then the code included linear regression on each relationship, separating them into Northern Hemisphere and Southern Hemisphere:

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots there is an explaination of what the linear regression is modeling and a short analysis for it.


### Part II - VacationPy

in this code,it's been tried to initially show the humidityof cities in Part I and then find ideal weather condition among those cities. Finally the code finds a hotel located within 5000 meters of the ideal cities coordination. To accompolish this goal, the jupyter-gmaps and the Google Places API is used in the code.

* **Note:** if you having trouble displaying the maps try running `jupyter nbextension enable --py gmaps` in your environment and retry.

* Thew code narrows down the cities in part I to find ideal weather conditionbased on these conditions:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

The code used Google Places API to find the first operational hotel for each city located within 5000 meters of the coordinates of the city with ideal weather condition.

* Then the code plots the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

* **Note:** 
If you would like to run the codes you need :
  1. To get api keys for [OpenWeatherMap API](https://openweathermap.org/api) & google maps API
  2. To create a folder named config in the root of the project and add a file named auth.ini inside config folder. Then inside the auth.ini file add this code including your API keys:
      
      [OpenWeatherMap]
      weather_api_key = your key here

      [GoogleAPIKey]
      g_key = your key here