---
layout: page
title: Walkability Mapping
permalink: /projects/walkability-mapping/
description: A walkability analysis of a city of your choice using only OSM open data and python code. 
img: assets/img/walkability_thumbnail.PNG
importance: 1
category: Mapping
lang: en
--- 

## Project Description
Cities love to talk about walkability. But how walkable is a city in practice when daily mobility depends so heavily on public transport?
This project explores that question by producing a spatial walkability score based on access to public transport stops, using only OSM open data and geospatial tools.

*This code was heavily inspired by Afagh Zeydani on Linkedin. Lots of credit goes to him for his work and for sharing it with the community.*

## What you'll expect
- A walkability score in a box of a sqm of your choice
- A map of the city with the walkability score + transport stops
- An automatic html map generation 

## How to use it
My code is very intuitive. All you need to do is modify the location name in the beginning of the code and run it! 

*Please respect the format : "City, Country"*

## Example
```python
city = "Amsterdam, Netherlands"
```

## Result
<iframe src="/assets/html/amsterdam_walkability_map.html" width="100%" height="500px" style="border:none;"></iframe>

## Interested in reusing the code ? 

<!-- Button Style (Same as About Page) -->
<style>
.btn-flip {
    background-color: #539eac !important;
    color: white !important;
    padding: 12px 35px;
    border-radius: 50px;
    font-size: 1.1rem;
    font-weight: 500;
    letter-spacing: 0.5px;
    box-shadow: 0 4px 10px rgba(83, 158, 172, 0.4);
    text-decoration: none !important;
    border: none !important;
    display: inline-block;
    transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.btn-flip:hover {
    background-color: #ad606b !important; /* Pink on hover */
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: rotateX(360deg); 
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://github.com/kalmahj/Walkability" target="_blank" class="btn-flip">
        <i class="fab fa-github"></i> Get the Code on GitHub
    </a>
</div>

<div style="text-align: center; margin-top: 50px; margin-bottom: 50px;">
    <p>Or copy this python code and paste it on your coding environment !</p>
    <details>
        <summary class="btn-flip" style="cursor: pointer; list-style: none;">Reveal the code</summary>
        <div style="text-align: left; margin-top: 20px;" markdown="1">

```python
"""
Created on Tue Nov  4 09:39:09 2025

@author: Kalma Hazara
"""

import osmnx as ox # OpenStreetMap API
import folium # To create a webmap
import geopandas as gpd
from shapely.geometry import box 
from shapely.geometry import Point 
import pandas as pd
import utm
import branca.colormap as cm

###############################################################################
## STEP 1: DEFINE OUR CITY ##

city = "Amsterdam, Netherlands"

###############################################################################
## STEP 2: VISUALIZATION OF CITY BOUNDARY ##

# Transform our OSM polygon into geodataframe
gdf = ox.geocode_to_gdf(city)

# Get the central coordinates of the city
lat, lon = gdf.geometry.centroid.y[0], gdf.geometry.centroid.x[0]

# Create the map and zoom on the central coordinates of our city
city_boundary = folium.Map(location=[lat, lon], zoom_start = 12, tiles = 'OpenStreetMap')

# Add our city polygon layer on our webmap
folium.GeoJson(gdf).add_to(city_boundary)

# Save and visualize the map
city_boundary.save(r"C:\Users\Pc\Downloads\city_walkability.html")

###############################################################################
## STEP 3: CREATION OF GRID SQUARES FOR MAP ##

# I recall the city polygon from Open Street Map
study_city = ox.geocode_to_gdf(city)

# I determine a specific EPSG for a given country   
utm_zone = utm.from_latlon(lat, lon)[2]
epsg = 32600 + utm_zone
study_city = study_city.to_crs (epsg=epsg)
                                
# Determine the size of our squares
grid_size = 1000 # 1km x 1km

# Draw a box around our study city
minx, miny, maxx, maxy = study_city.total_bounds

# Create squares automatically inside our box
grid_cells = []
x = minx
while x < maxx :
    y = miny
    while y < maxy :
        grid_cells.append(box(x, y, x + grid_size, y + grid_size))
        y += grid_size
    x += grid_size
    
# Convert our squares into geodataframe using Geopandas
grid = gpd.GeoDataFrame({'geometry': grid_cells}, crs = study_city.crs)

# Clip our grid map according to the shape of our city polygon
grid = gpd.overlay(grid, study_city, how = 'intersection')

###############################################################################
## STEP 4: RETRIEVE POIs FROM OPEN STREET MAP

# Ensure that my city layer is not segmented
polygon = gdf.geometry.union_all()

# Write the OSM query to retrieve public transport POIs
tags = {
    "public_transport": ["station", "stop_position", "platform"],
    "railway": ["station", "halt", "tram_stop", "subway_entrance"],
    "highway": ["bus_stop"]}

# Download POIs from Open Street Map
pois = ox.features_from_polygon(polygon, tags)

# Remove empty rows
pois = pois.dropna(subset=["public_transport", "railway", "highway"], how="all")

# Reproject to the grid's UTM
pois = pois.to_crs(epsg=epsg)

###############################################################################
## STEP 5: CALCULATE WALKABILITY SCORE ##

# Create a centroid on each tile to be able to measure distances to POIs
grid['centroid'] = grid.geometry.centroid

# Create distance thresholds for walkability
thresholds = [400, 800, 1200] # these are values in meters

# Creation of an empty column for the walkability score of each tile
grid['raw_score'] = 0

# Distance calculation loop for each square's centroid 
for i, centroid in grid['centroid'].items():
    # Measure the distance between the centroid and the POIs
    dists = pois.geometry.distance(centroid)
    
    # Reset the square's score
    score = 0
    
    # According to its distance, we assign it a score
    for d in dists:
        if d <= 400:
            score += 3 # Add 3 points if very close (less than or equal to 400m)
        elif d <= 800:
            score += 2 # Add 2 points if moderately close (between 400 and 800m)
        elif d <= 1200:
            score += 1 # Add 1 point if less close (between 800 and 1200)
        else:
            score += 0 # If the distance is beyond 1200m, add 0 points
            
    # Add the score to the square
    grid.at[i, 'raw_score'] = score

###############################################################################
## STEP 6: CONVERT TO VALUE BETWEEN 0 and 100

# Normalization of the result
# Inspired by this code: https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html
grid["final_score"] = 100 * (grid['raw_score']-grid['raw_score'].min()) / (grid["raw_score"].max()-grid["raw_score"].min())

###############################################################################
## STEP 7: VISUALIZATION OF THE FINAL MAP WITH FOLIUM ##

# Conversion of CRS to WGS84 for folium
grid_wgs84 = grid.to_crs(epsg=4326)
pois_wgs84 = pois.to_crs(epsg=4326)

# Creation of the base map
# I use CartoDB positron for a minimalist base map
# We center the map on the city coordinates defined earlier.
walkability_map = folium.Map(location=[lat, lon], zoom_start=12, tiles='OpenStreetMap')

# Styling of the title with HTML
title_html = f'''
<div style="
    position: fixed; 
    top: 20px; 
    left: 50px; 
    width: 350px; 
    background-color: rgba(255, 255, 255, 0.9); 
    border-left: 5px solid #2c3e50;
    z-index: 9999;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 22px;
    font-weight: bold;
    color: #2c3e50;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    ">
    Walkability: {city}
    <div style="font-size: 14px; font-weight: normal; margin-top: 5px; color: #7f8c8d;">
        Public Transport Accessibility Analysis
    </div>
</div>
'''
# We add this HTML element to the map
walkability_map.get_root().html.add_child(folium.Element(title_html))

# Creation of the legend with colormap because I can manually determine the colors
colormap = cm.LinearColormap(
    colors=['#d7191c', '#fdae61', '#ffffbf', '#a6d96a', '#1a9641'], # Red -> Green
    vmin=grid_wgs84['final_score'].min(), # Minimum value of our data
    vmax=grid_wgs84['final_score'].max(), # Maximum value of our data
    caption='Walkability Score (0 = Low, 100 = High)' # Legend title
)

# Adding tiles (grid) to the map
# I add it in a Feature group so the user can check/uncheck this layer
tile_group = folium.FeatureGroup(name='Walkability Score', show=True)

# Loop through each square in our data table to add it to the map
for idx, row in grid_wgs84.iterrows():
    # We retrieve the score and geometry of the square
    score = row['final_score']
    geometry = row['geometry']
    
    # We determine the square's color using our palette (colormap) defined above
    square_color = colormap(score)
    
    # We add the square as GeoJson
    folium.GeoJson(
        geometry,
        style_function=lambda x, color=square_color: {
            'fillColor': color,      # Fill color according to score
            'color': 'white',        # Border color of the square (white for a clean look)
            'weight': 0.5,           # Border thickness
            'fillOpacity': 0.6       # slightly transparent
        },
        # The tooltip displays on mouse hover
        tooltip=f"Score: {score:.1f} / 100"
    ).add_to(tile_group)

# Once all squares are added to the group, we add the group to the main map
tile_group.add_to(walkability_map)

# We do the same for transport stops
pois_group = folium.FeatureGroup(name='Transport Stops', show=True)

# Loop through each point of interest found
for idx, row in pois_wgs84.iterrows():
    # We try to retrieve the stop's name, otherwise we put "Transport" by default
    name = row.get('name', 'Transport')
    
    # We customize the color and icon according to the transport type
    # This makes the map more readable and informative
    if pd.notna(row.get('public_transport')):
        color = '#3498db' # Blue for generic bus/trams
        transport_type = "Public Transport"
    elif pd.notna(row.get('railway')):
        color = '#e74c3c' # Red for trains/metros
        transport_type = "Railway"
    else:
        color = '#2ecc71' # Green for others (simple bus stops)
        transport_type = "Bus Stop"
    
    # We only want to retrieve points
    if row.geometry.geom_type == 'Point':
        # We add a circular marker
        folium.CircleMarker(
            location=[row.geometry.y, row.geometry.x], # Latitude, Longitude
            radius=5,                   # Point size
            popup=f"<b>{name}</b><br><i>{transport_type}</i>", # Window that opens on click (with HTML)
            color='white',              # White border to stand out
            weight=1,                   # Border thickness
            fill=True,                  # Fill the circle
            fillColor=color,            # Interior color defined above
            fillOpacity=0.8             # Transparency
        ).add_to(pois_group)

# We add the POIs group to the map
pois_group.add_to(walkability_map)

# We add the color legend in the top right of the map
colormap.add_to(walkability_map)

# We add the layer control panel (in the top right)
folium.LayerControl(collapsed=False).add_to(walkability_map)

# Finally, we save the result in an interactive HTML file
output_path = r"C:\Users\Pc\Downloads\amsterdam_walkability_map.html"
walkability_map.save(output_path)
```
        </div>
    </details>
</div>