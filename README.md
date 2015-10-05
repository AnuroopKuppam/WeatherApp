#Weather App

A lightweight weather information app. It fetches the weather data from [openweather] (http://openweathermap.org/). 
The user has the ability to change the temperature information from Celsius to Farenheit and also one can change 
the location via the PIN/ZIP code preferences in the settings tab.


#####Working of the APP
It fetches the weather information from [openweather] (http://openweathermap.org/) as json via a thread. It passes
the infromation to the main UI thread for parsing the JSON (this is infact the most efficient way to do it!).
The queries to [openweather] (http://openweathermap.org/) are sent depending on the users preferences of location
and then the temparature is converted either to Celsius or Farenheit. The information is displayed as ```listview``` by the
```MainActivity``` and the ```onItemClick``` for the ```listview``` will display the weather forecast in more detail by 
```DetailActivity```. By using *explicit* ```Intent``` the data can be passed between the ```ForecastFragment```
and the ```DetailActivity```.

######To-Do List
1. Capture more weather data like the humidity and precipitation.
2. Right now the weather for the next seven days is displayed. Increase it for 30 days. That means recycling the ```listview```
  objects.
3. Make it more user friendly by allowing the user to enter the city name and country rather than ZIP/PIN code and saving
the preferences.

######Thoughts
Android development draws heavy parallels to the **MVC** design paradigm. The *activities* can be thought as equivalent to
the *controllers* and  as every *controller* has a corresponding *view* associated with it so does each activity defined
as ```layout``` in XML. But Android emphasizes heavily on the *lifecycle* of each activity to prevent overuse of memory.
