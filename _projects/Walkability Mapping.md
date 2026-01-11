---
layout: page
title: Walkability Mapping
permalink: /projects/walkability-mapping/
description: A walkability analysis of a city of your choice using only OSM open data and geospatial tools. 
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
- An automatic folium map generation 

## How to use it
My code is very intuitive. All you need to do is modify the location name of your chose in the beginning of the code and run it! 

*Please respect the format : "City, Country"*

## Example
```python
city = "Amsterdam, Netherlands"
```
## Libraries used
- osmnx
- folium
- geopandas
- shapely
- pandas
- utm
- branca

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