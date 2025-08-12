# 🏙️ Coursera_Capstone  
**Finding the Most Convenient Neighbourhoods to Live in Calgary, Alberta, Canada**

## 📖 Project Overview  
As many immigrants move to Canada, choosing the right neighborhood without local connections can be tough. This project analyzes neighborhoods in Calgary based on multiple factors to help newcomers find the most convenient places to live.  

**Key parameters considered:**  
- 🚍 Transit Access  
- 🚨 Crime Rate  
- 🌳 Park Access  
- 🍽️ Restaurants and Bar Access  

Check out the full article here: [LinkedIn Article](https://www.linkedin.com/pulse/finding-most-convenient-neighborhoods-live-calgary-maryam-vahdat-pour/)

## 🗃️ Data Sources  
- **Foursquare API:** Restaurants, bars, and parks data per neighborhood  
- **Calgary Transit Scheduling Data:** Stops and routes info ([Dataset](https://data.calgary.ca/Transportation-Transit/Calgary-Transit-Scheduling-Data/npk7-z3bj))  
- **Community Crime and Disorder Statistics:** Crime rates by neighborhood ([Dataset](https://data.calgary.ca/Health-and-Safety/Community-Crime-and-Disorder-Statistics/848s-4m4z))


## 🛠️ Methodology  
This project is structured into 7 main steps:

1. **Scraping Calgary Neighbourhoods:** Extract neighborhood names from Wikipedia.  
2. **Getting Latitudes and Longitudes:** Scrape geolocation data for each neighborhood.  
3. **Preprocessing Transportation Data:** Clean and prepare transit data.  
4. **Calculating Number of Stops per Neighborhood:** Use Voronoi diagrams to assign bus stops to neighborhoods based on location.  
   - More info: [SciPy Voronoi Diagram](https://docs.scipy.org/doc/scipy-0.18.1/reference/generated/scipy.spatial.Voronoi.html)  
5. **Preprocessing Crime Dataset:** Aggregate crime counts by neighborhood.  
6. **Scraping Foursquare Data:** Gather counts of restaurants, bars, and parks per neighborhood.  
7. **Analyzing Final Dataframe:**  
   - Normalize features (stops, crime, parks, restaurants) on a scale from 0 to 10.  
   - Adjust crime score (higher crime → lower score).  
   - Compute overall score and identify top 10 neighborhoods.  
   - Use clustering to group neighborhoods by similar features and suggest alternatives.


## 📊 Results  
**Top 10 Neighborhoods to Live in Calgary:**  

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


## 💬 Discussion  
- Scores are equally weighted averages of features.  
- Clustering helps group neighborhoods with similar profiles, enabling personalized selection based on preferences.  
- Users can pick the best neighborhood from each cluster according to their priorities.


## 📝 Conclusion  
This project provides a data-driven approach to rank Calgary neighborhoods by convenience. Future improvements can include weighted scoring based on individual preferences to offer tailored recommendations.
