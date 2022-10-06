library(knitr)
library(leaflet)
library(dplyr)
m <- leaflet() %>%
  addTiles() %>%  # Add default OpenStreetMap map tiles
  addMarkers(lat=28.6129, lng=77.2295, popup="India Gate, Delhi") %>%
  addMarkers(lat=28.5244,lng=77.1855, popup="Qutb Minar, Delhi") %>%
  addMarkers(lat=28.6562,lng=77.2410, popup="Red Fort, Delhi") %>%
  addMarkers(lat=28.5933,lng=77.2507, popup="Humayun's Tomb, Delhi") %>%
  addMarkers(lat=28.6264,lng=77.2089, popup="Gurudwara Bangla Sahib, Delhi") %>%
  addMarkers(lat=28.6127,lng=77.2773, popup="Akshardham, Delhi") #%>%
  #setView (lat=28.6129, lng=77.2295, zoom=16) 
  
m  # Print the map
df <- data.frame(lat=runif(500, min=28.65, max = 28.75 ),
                 lng=runif(500, min=77.05, max = 77.15 ))  
df %>%
leaflet() %>%
addTiles() %>%  
addMarkers(clusterOptions = markerClusterOptions())  
                 
                 
                 