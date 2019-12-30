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
Methodology section which represents the main component of the report where you discuss and describe any exploratory data analysis that you did, any inferential statistical testing that you performed, if any, and what machine learnings were used and why.
