# Vegetarian Restaurant Business in Toronto, Canada

## Introduction and Business Problem

For the interest of __vegetarian__, a business in terms of __restaurant__ is considered. The restaurant would be located __in Toronto__ for the convenience to its owner and its important role in Canada. This is a big city, it is definitely hard to choose __a location__ for a restaurant business. Customer behaviours will be studied in this work in order to get the insight information about which __specific area__ customers in Toronto are interested in vegetarian food. In order to be successful, understanding of demographics is a good practice to do. 

__The aims__ of this work will then attempt to answer some following questions:

1. Which area in Toronto, people are interested in a __vegetarian restaurant?__
1. How about __demographics data__, be specific for a relevant neighbourhood.
1. __A specific location__ should be answered in this work.
1. What should we __prepare__ for a new restaurant business here? What __language__ we need to prepare for our staff before running a restaurant.

Some findings would be found in the study to give relevant information to those questions.

## Who this study for?

1. __A vegetarian__ who is keen on vegetarian food to search for restaurants.
1. __An entrepreneur__ who is interested in doing a restaurant business in terms of vegetarian.
1. __Language centres and communities__ to prepare suitable courses for language training. 
1. For those who work for __hospitality industry__ as some findings in the study might be found relevant.
1. Data scientists as references.

# Data

1. Neighbourhoods in Toronto
https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M (A list of postal codes of Toronto)

2. Geospatial data to get latitude and longitude of neighbourhoods
https://cocl.us/Geospatial_data (To get information about latitude and longitude of a certain code.)

3. Foursquare to get venues in a specific area. 
https://developer.foursquare.com/ (APIs to provide information about venues, specific venue photos, details and reviews from customers)

4. Toronto Demographics from Open Government Toronto
https://open.toronto.ca/dataset/wellbeing-toronto-demographics/ (Data last refreshed: Feb 28, 2017) (Demographics data in terms of population, language, age, gender)

# Methodology

## Data acquisition

Neighbourhoods information are acquired from <a href="https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M">a list of postal codes</a>. Based on post codes, those data will be merged with latitude and longitude which are found at <a href="https://cocl.us/Geospatial_data">Geospatial data</a>.

A geocoder - Nominatim is employed in this work to fetch latitude and longitude of some specific places. Particularly, to get geo information about Toronto, Canada for showing a map.

To acquire details of areas such as venues, categories of venues, API requests were sent to Foursquare to retrieve information. Requests were repeated for all of the areas with indeed defined CLIENT_ID, CLIENT_SECRET, VERSION. Foursquare would return 100 venues data within 1 kilometre near each neighbourhood.

Demographics data will be fetched from Open Government Toronto website for analysis purpose. 


## Data preparation

Some data rows from a list are missed their borough, they are therefore removed for data consistency. Those remain rows will be checked to rename their column names to be fitted with 2 data frames from different data sources (List of Postal Codes and Geospatial Data). As a result "Post Code" column is renamed to be "Postcode" in order to be correctly merged. 

Due to the requirement of a business, only areas in Toronto will be considered, others were removed to produce a clear data frame. 

Retrieved records from Foursquare were filtered to keep relevant information: name, categories, latitude and longitude of venues. Data were treated to be binary flags for each type of category and sorted accordingly how people frequently visit them. For those records have not be found in Foursquare, they were being removed to keep data clean. 

Data from Open Government Toronto was extracted to CSV file, loaded to code and renamed columns for readability and chart plotting.


## Data Exploratory and Analysis

Neighbourhoods would be clustered with __Machine Learning technique (k-means algorithm)__ accordingly its venues characteristics, for example, a kind of a venue, and how people visit that venue. Those neighbourhoods were divided into 5 clusters and presented on the map for readability. Chart plotting techniques are also employed to visualise information effectively in order to easily recognise the correlation between objects.

# Results

A map below shows areas were examined in this work. Those belong to Toronto city. __A cluster numbered 3 (blue marks)__ are recognised to be fitted with the business requirement as people in __those neighbourhoods often visit vegetarian restaurant__ including The Annex, North Midtown, Yorkville, Harbord, University of Toronto, Chinatown, Grange Park, Kensington Market. In other clusters (1,2,4,5), there is not found that a vegetarian restaurant is a good option for the population there. 

<img src="https://github.com/wil-di-venezia/applied-data-science/blob/master/assets/map.png" />

As a good business tends to attract relevant people, we would need to know top neighbourhoods people would like to visit a vegetarian restaurant. Top 3 neighbourhoods are found: Chinatown, Grange Park, Kensington Market, people in these areas have same the interests in terms of regarding their Most Common Venue. 

<img src="https://github.com/wil-di-venezia/applied-data-science/blob/master/assets/top_vegan_restaurant_venues.png" />

According to data from Open Government Toronto, __3 top neighbourhoods found (Chinatown, Grange Park, Kensington Market) are belong to JUST one area named Kensington-Chinatown__. As the below graph, we can see __non-native speakers__ have occupied a large part of the population in this area, approximately __96%__. 

<img src="https://github.com/wil-di-venezia/applied-data-science/blob/master/assets/population.png" />

As the below bar chart, __the Chinese language__ is recognised to be the highest bar with approximately __600 people__ speaking this language. 9 other languages are significantly low represented. 

<img src="https://github.com/wil-di-venezia/applied-data-science/blob/master/assets/languages.png" />

# Discussion

__Kensington-Chinatown in Toronto__ should be found as a good place to set up a business restaurant in terms of __vegetarian__. Because it is the __3rd most people tend to visit__. As there are __96% of the population__ would prefer to speak their languages __(not English or French)__, businesses, therefore, should prepare themselves to be ready for languages exchange activities and training; or they can speak the language of a guest for good. __Chinese is the most powerful language in this area__ because people speaking Chinese here approximately __35%__. We would think about what we should serve in our vegan restaurants. Studying the above bar graph, the Chinese language could be represented for Chinese people here. It is therefore suggested to consider __Chinese cuisine__ for those who tend to set up vegan restaurant businesses.

For those who work for the __hospitality industry__, some relevant information could be seen here as not only for restaurant but other businesses would be suggested to concern about services to adapt with __Chinese culture__ in order to attract an appropriate targeted group of visitors.

# Conclusion 

The study has attempted to apply knowledge of __data analysis, visualisation and also machine learning__ in terms of __clustering__ based on characteristics of objects. Those are respected to __business problem-solving__ as data would be shown clearly and readability. __Data is crucial__ to explore and discover to attain correct findings. Hence, __data preparation should be conducted with integrity methods despite time-consuming task considered.__

