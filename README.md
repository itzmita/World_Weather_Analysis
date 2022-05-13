# World_Weather_Analysis

## Overview of Project
In this project we collected weather data for a hypothetical travel company, PlanMyTrip using Weather API. We also used Google API to create heatmaps and searched places for vacation based on certain temperature criteria. We retrieved specific information from websites using application programing interface (API) from 2000 random cities around the world. The expected deliverables for this project are:

	• Retrieve Weather Data
	• Create a Customer Travel Destination Map
	• Create a Travel Itinerary Map


## Data Source Information
The data source used in this project was retrieved from OpenWeatherMap website, Google gmaps and the statistical analysis was performed with Citipy Library.
Software
Python 3.7.6, Pandas Library, Matplotlib, Jupyter Notebook, Numpy, APIs and JSON.



## Results

### Retrieve Weather Data
We generated latitudes and longitudes of 2000 random cities and created a DataFrame. Using the citipy module, we searched for the nearest cities for those latitudes and longitudes. Next we made an API call with OpenWeatherMap using each of those 2000 cities and retrieved various information from the API response. These details were then stored in a DataFrame which is shown as below. We stored this DataFrame in a WeatherPy_database.csv file which will be used in the next step.

![image](https://user-images.githubusercontent.com/3753839/168202953-ba67fe85-91ee-4155-a819-e1abc2e764b4.png)


### Create a Customer Travel Destinations Map
In the next step we created a DataFrame using the csv file from the 1st step. We requested for user input for weather preferences such as Max and Min temperature. Using these values we searched in the DataFrame using loc method against the "Max Temp" column to pull rows which fits the user criteria. This filtered dataframe was copied into a hotel DataFrame where we added an empty column "Hotel Name". To search for Hotel Name we used the Google Directions API. This  API used latitude longitude combined together as location parameter. We also used the type of search to be "lodging" to ensure we pull hotels in the search. The response of the API call gave us potential travel destinations along with nearby hotels. The destinations are identified with a marker layer map with pop-up markers. The final dataframe along with the Hotel Name was also stored in a WeatherPy_vacation.csv file for the next step.

![image](https://user-images.githubusercontent.com/3753839/168203012-8d2f67cc-e99a-474b-abc3-bf09bb6563a1.png)


### Create a Travel Itinerary Map
In this step we loaded the prior step csv file in a dataframe.

![image](https://user-images.githubusercontent.com/3753839/168203044-b39a54ba-b96e-436e-9dd9-55e3dc824213.png)

Next we had to choose any 4 cities that a customer would want to visit and create an Itinerary. We used the loc method to create 4 separate dataframes. We collected the latitudes and longitudes for each of those 4 cities. Next used the gmaps method we created a directions layer map using those 4 city data.  Here is a snapshot of the direction layer that got created.

![image](https://user-images.githubusercontent.com/3753839/168203066-69c5c352-1d67-4492-8438-132735c89b5e.png)



We concatenated the 4 cities dataframe into one dataframe. Next we create a marker layer map and pop-ups were added to provide all the details to the user. The pop ups had the name of the city, country, hotel and current weather description. Here is a screenshot of the same. 

![image](https://user-images.githubusercontent.com/3753839/168203084-c59d6401-284c-4f07-897f-93711ad0e793.png)

