---
layout: page
title: 3D Building Modelling
permalink: /projects/3d-building-modelling/
description: A multipatch 3D building model created using LiDar points and ArcGIS geoprocessing tools.
img: assets/img/lidar_thumbnail.PNG
importance: 1
category: Mapping
lang: en
---

## Project Description
LiDar data is a powerful tool for creating 3D models of objects. In this project, I used LiDar data and ArcGIS geoprocessing tools to create a multipatch 3D model Gulpen, Netherlands using ArcGIS Pro. 

## What is Lidar data?
Light Detection and Ranging (lidar) is a technology used to create high-resolution models of ground elevation with a vertical accuracy of 10 centimeters (4 inches). Lidar equipment, which includes a laser scanner, a Global Positioning System (GPS), and an Inertial Navigation System (INS), is typically mounted on a small aircraft. 

The laser scanner transmits brief pulses of light to the ground surface. **Those pulses are reflected or scattered back and their travel time is used to calculate the distance between the laser scanner and the ground** 

Lidar data is initially collected as a “point cloud” of individual points reflected from everything on the surface, including structures and vegetation. To produce a “bare earth” Digital Elevation Model (DEM), structures and vegetation are stripped away (USGS, 2022).

For example, modern cars use LiDar data to navigate through cities, or sense sudden obstacles on the road a normal camera can't catch.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/lidar.jpg" title="Lidar data example" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## How to get Lidar data?
If you are in the US, you can access Lidar data from the USGS (US Geological Survey).
<!-- Button Style (Consolidated) -->
<style>
.btn-zoom {
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
    transition: all 0.3s ease-in-out;
}

.btn-zoom:hover {
    background-color: #ad606b !important; /* Pink on hover */
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: scale(1.05); 
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="http://apps.nationalmap.gov/lidar-explorer/#/" target="_blank" class="btn-zoom">
        Click here to access US Lidar data
    </a>
</div>

If you are in France, I highly recommend you use the 3D Lidar by IGN (Institut Géographique National). It is a free service provided by the French government.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://geoservices.ign.fr/lidarhd" target="_blank" class="btn-zoom">
        Click here to access French Lidar data
    </a>
</div>

If you are in the Netherlands, I highly recommend you use the 3D Lidar by Actueel Hoogstebestand Nederland (AHN). It is a free service provided by the Dutch government. 

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.ahn.nl/dataroom" target="_blank" class="btn-zoom">
        Click here to access Dutch Lidar data
    </a>
</div>

## Result 
<video width="100%" controls>
  <source src="/assets/img/3d_arcgis.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Interested in following the tutorial?

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://learn.arcgis.com/fr/projects/extract-3d-buildings-from-lidar-data/" target="_blank" class="btn-zoom">
        Click here to access tutorial
    </a>
</div>