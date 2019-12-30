# Coursera_Capstone

**Finding Most Convenient Neighbourhoods to Live in Calgary, Alberta, Canada.**

### Introduction to the Problem

Since many people immigrated to Canada in the last decades, and most of them have no relatives there, the main problem is finding a good neighborhood based on their needs. As one of the immigrants, I would compare different neighborhoods in Calgary, Alberta based on different parameters. Here is the list of parameters that are considered to suggest the best neighborhoods in Calgary:

    1. Transit Access
    2. Crime Rate
    3. Park Access
    4. Restaurants and bar Access

Hopefully, this study helps immigrants to find the most convenient neighborhood for them to live in Calgary.



### DATA

* In this problem, I will use the Foursquare dataset to find restaurants, bars, and parks in each neighborhood in Calgary.

* I would also use the publicly available dataset on **Calgary Transit Scheduling Data** from here: https://data.calgary.ca/Transportation-Transit/Calgary-Transit-Scheduling-Data/npk7-z3bj

  This dataset contains five files, including `trips.txt`, `shapes.txt`, `stop_times.txt`, `stops.txt`, `calendar.txt`, `routes.txt`, `calendar_dates.txt` and `agency.txt`. In this project, probably I will use `stops.txt` as the main file to explore.

* Also, I will use **Community Crime and Disorder Statistics** data which is also publicly available here: https://data.calgary.ca/Health-and-Safety/Community-Crime-and-Disorder-Statistics/848s-4m4z

This dataset contains `Sector`,    `Community Name`,    `Group Category`,    `Category`,    `Crime Count`,    `Resident Count`,    `Date`,    `Year`,    `Month    ID`, `Community` and `Center Point`. I will also use most of these columns to gather information about the rates in different neighborhoods.



### Methodology

In this report, I have 7 main sections:

     1. Scraping Calgary Neighbourhoods
     2. Scraping the latitude and longitude of each neighbourhood in Calgary
     3. Preprocessing Transportation dataset 
     4. Calculating Number of Stops per Neighbourhood
     5. Preprocessing Crime dataset 
     6. Scraping Foursquare dataset for Restaurants and Parks
     7. Analyzing Final Dataframe 

To do the scraping and preprocessing the datasets, I used python scraping and preprocessing features and libraries. 

In sections 1 and 2, I used the `Wikipedia` website to scrape the neighborhoods and their latitude and longitude.

In section 3, I cleaned and preprocessed the Transportation dataset.

In section 4, I used the Voronoi Diagram, to find the number of bus stops in each neighborhood. The `Voronoi` diagram of a set of seed points divides space into several regions. Each region contains all points closer to one seed point than to any other seed point.

I used this diagram to find each stop in each neighborhood using `latitude` and `longitude` of each neighborhood.

You can read more about `Voronoi` Diagram via SciPy here: 

https://docs.scipy.org/doc/scipy-0.18.1/reference/generated/scipy.spatial.Voronoi.html

Section 5 also preprocessed the crime dataset to have the total amount of crimes in each neighborhood.

To have information about parks and restaurants, section 6 scrapes the data from Foursquare API.

After cleaning and preprocessing the data in all last 6 sections, the dataset includes the following features:

     1. Neighbourhood	
     2. Quadrant	
     3. Type	
     4. Area	
     5. latitude	
     6. longitude	
     7. number_of_stops	
     8. crime_count	
     9. number_of_parks	
     10. number_of_restaurants

To analyze the data in section 7, first, I normalized the amount of `number_of_stops`, `crime_count`,  `number_of_parks`  and `number_of_restaurants` to have a score for each row. After having all normalized scores between 0 and 10, I considered the crime rate score as `10 - crime_count`, because of the more `crime_count` the worse neighborhood. Finally, I calculated the mean of each row based on the scores, and then suggest the top 10 neighborhoods based on that.

Furthermore, I used the clustering algorithm to cluster the neighborhoods based on these aforementioned features, and suggest the other neighborhoods in the same cluster with the top 10.


### Results

As it is shoen in the note book, here are the top 10 neighbourhoods to live in Calgary:
	
     1. BELTLINE	
     2. MISSION	
     3. DOWNTOWN COMMERCIAL CORE	
     4. OGDEN	
     5. SUNDANCE	
     6. SOUTHVIEW	
     7. CANYON MEADOWS	
     8. MOUNT PLEASANT	
     9. ST. ANDREWS HEIGHTS	
     10. MAYFAIR

### Discussion

After normalizing the features, I specified a score for each row, which is the average number of each row, to have a better measure for each neighborhood to compare them together. However, one might think of the priority of any other feature in comparison with the other ones. To solve this problem, I used the clustering method, which suggests similar neighbourhoods in one cluster with similar features. This can help the users to find neighborhoods that have similar features, and pick the best of each cluster. After picking the best of each cluster based on their needs, they can sort them based on the top 10 clusters suggested by the scores.


### Conclusion
To conclude the report, In this study, we compared different neighborhoods in Calgary to find the top 10 ones. The strategy suggested the top 10 with considering all the features having the same weight. However, it could be scored using a weighted average based on user needs.
