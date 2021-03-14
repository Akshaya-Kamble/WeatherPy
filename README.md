# WeatherPy

## Overview of the project
PlanMyTrip  is a travel company and Jack is helping to create a beter website using Google API's. In this challenge we will identify potential travel destinations and nearby hotels depending on the input of maximum and minimum temperatures prefered by the users.From the list of potential cities filtered by all the criteria we will select four cities  to create a travel itinerary.Finally, using the Google Maps Directions API,we will create a travel route between the four cities as well as a marker layer map.

For this analysis we have used the following version of softwares and API websites.
Anaconda(python data) 4.8.5
Python 3.7.6 
Pandas,numpy, citipy, datetime for python using Jupyter notebook.
Google API
Openweathermap API
Finally updating the code to Github using Gitbash.

## Results
### Retrieve Weather Data

We have generated a set of 2,000 random latitudes and longitudes. Using these pairs of latitudes and longitudes we have retrieved the nearest city,current weather description for each city by performing an API call with the OpenWeatherMap.After collecting all the data we have a new DataFrame containing the updated weather data.

Using the following steps in the jupyter notebook we have retieved weather data using open weather map.
1. Create a set of random latitude and longitude combinations using np.random.uniform() and using zip() to get the pairs of latitude and longitude.
2. Create a list cities = [] for holding the cities and also getting a total count. 
3. Perform an API call with the OpenWeatherMap
4. Group cities in sets of 50 for logging purposes we will create a new list city_data that will have details for all the cities retrieved above. 
5. Convert this array of dictionaries from our result to a Pandas DataFrame.

city_data Image for reference
![](https://github.com/Akshaya-Kamble/WeatherPy/blob/main/Reference%20Images/city_data_df.png)	

6. For future projects we will convert the city_data_df to a WeatherPy_Database.csv and save it to the Weather_Database folder

 
We have all the data available in the Weather_Database folder with the following files:

#### 1. The Weather_Database.ipynb file
#### 2. The WeatherPy_Database.csv file

### Create a Customer Travel Destinations Map
In this part of the project we will ask the customer to input the prefered minimum and maximum temperature preferences.Then using those preferences to identify potential travel destinations and nearby hotels we will display these cities on a marker layer map with pop-up markers.

Using the following steps in the jupyter notebook we have retieved Customer Travel Destinations Map using Google API
1. Import the WeatherPy_Database.csv file from Weather_Database folder
2. Create input statements to get minimum and maximum temperature from the user.
3. Using the loc method to filter the city_data_df DataFrame for temperature criteria collected in Step 2, and create a new DataFrame.
4. Determine if there are any empty rows, then drop them using dropna() and create a new DataFrame.
5. Created a DataFrame called hotel_df to store hotel names along with city, country, max temp,Weather Description and coordinates.
6. Set parameters to search for hotels with 5000 meters using google key and update the Hotel Name of the hotel_df created in the previous step.Now since we    have the hotel names we can use them for ploting in the markers.

hotel_df Image for reference
![](https://github.com/Akshaya-Kamble/WeatherPy/blob/main/Reference%20Images/hotel_df.PNG) 
7. Drop rows where no hotel name was found.
8. Create csv file named WeatherPy_vacation.csv and save in folder named Vacation_search.
9. Add the city name, the country code, the weather description, and the maximum temperature for the city to the info_box_template 
10. Using list comprehension retrieve the city data from each row and saved in the hotel_info list.
11. Get the latitude and longitude from each row and store in a new DataFrame named locations.
12. Create a marker layer map that will have pop-up markers for each city on the map.
13. Save screenshot name WeatherPy_vacation_map.png to Vacation_Search folder

We have all the data available in the Vacation_Search folder with the following:

#### 1.The Vacation_Search.ipynb file
#### 2.The WeatherPy_vacation.csv file
#### 3.The WeatherPy_vacation_map.png image

### Create a Travel Itinerary Map
Using Google Directions API we have created a travel itinerary that shows the route between four cities chosen from the customer’s possible travel destinations.We have also created a marker layer map with a pop-up marker for each city on the itinerary.

Using the following steps in the jupyter notebook we have created travel itinerary with pop up markers
1. Import the WeatherPy_vacation.csv file from your Vacation_Search forlder
2. Adding the Hotel name, city name, the country code, the weather description and maximum temperature for the city in the info_box_template for the        markers.
3. Adding a marker layer for each city to the map.
4. From the map above we pick 4 cities and create a vacation itinerary route to travel between the four cities. and create DataFrames for each city by    filtering the 'vacation_df' using the loc method. 
5. Get the latitude-longitude pairs as tuples from each city DataFrame using the to_numpy function and list indexing.
6. Create a direction layer map using the start and end latitude-longitude pairs with stop1, stop2, and stop3 as the waypoints.We have selected the    travel_mode as "DRIVING"
7. Create a marker layer map between the four cities and combine the four city DataFrames into one DataFrame using the concat() function.
8. Adding city name, the country code, the weather description and maximum temperature for the city to info_box_template.
9. Add a marker layer for each city to the map and display the map with the cities selected.

We have all the data available in the Vacation_Itinerary folder with the following:

#### 1.The Vacation_Itinerary.ipynb file
#### 2.The WeatherPy_travel_map.png image
#### 3.The WeatherPy_travel_map_markers.png 

## Summary
With help of Python data and dependencies we are able to collect data, plot data on google maps with cities and markers using google API .


[1]:https://github.com/Akshaya-Kamble/WeatherPy/blob/main/Reference%20Images/city_data_df.png
[2]:https://github.com/Akshaya-Kamble/WeatherPy/blob/main/Reference%20Images/hotel_df.PNG
