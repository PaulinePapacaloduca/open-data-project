# Appendix

We based this study on listings data from [Inside Airbnb](http://insideairbnb.com/get-the-data.html). The [CSV file](http://data.insideairbnb.com/portugal/lisbon/lisbon/2019-11-28/visualisations/listings.csv) gives summary information and metrics for listings in Lisbon, and was compiled on November 28, 2019. 
We analyzed the data on Excel and QGIS. We first cleaned the data, and removed missing values. Then we decided to filter the data to keep listings in Lisbon only (neighborhood_group = Lisboa), and filtered to entire home listings only for the analysis (room_type = Entire home/apt).

**Map of listings:**
On QGIS, we created a layer of delimited text with the listings csv using the latitude and longitude variables as coordinates. As above, we filtered entire home listings in Lisbon only. Then, we used a gradient symbol that we based on the price, using quantiles as color categories. For the buildings and boundaries of Lisbon, we used OpenStreetMap vector tiles retrieved from [OpenMapTiles](https://openmaptiles.com/downloads/dataset/osm/europe/portugal/lisbon/#8.44/38.7551/-9.046). This allowed us to use buildings as a reference for the location of Airbnb in Lisbon (places where there are no listings actually are places where there are no residential buildings at all).

**Availability graph:**
On Excel, we used a dynamic cross table of the total number of listings for each availability period, based on the variable “availability_365”. Based on that, we created the histogram. However, we assimilated listings available 0 days with missing values and removed them, because they distorted the graph (there were a total of 1153 listings available 0 days) and didn’t bring any usable information.

**Top 10 hosts table:**
On Excel again, we created a dynamic cross table of the number of listings for each host ID (“host_id” variable), then relating each host ID to its host name (“host_name” variable). We kept only the 10 first host IDs with the highest number of listings.

**Top 4 hosts map:**
On QGIS, we selected the listings of each of the four hosts with the highest number of listings that we identified previously (Feels like Home, Rent Experience, Homing and LxWay). We created a layer for each of these hosts, that we colored differently to identify them more easily.

**Numbers and prices graph:**
On Excel, we used a dynamic cross table to calculate the total number of listings and the average price per night (“price” variable) in each neighborhood (“neighborhood” variable). Then, we plotted on the same graph the number of listings as vertical bars and the average price per night as a curve. We decided to compare average prices per night with real estate prices to see if there was any correlation. We retrieved data about real estate prices in each neighborhood [this website](https://www.google.com/amp/s/www.lisbob.net/fr/blog/carte-prix-immobilier-lisbonne-portugal-2019%3fformat=amp) and we added them to the graph as a curve. The graph uses the same scale for the number of listings and the price per m<sup>2</sup> and a different scale for the price per night. 
