---
layout: page
title: Zombification Risk Mapping
permalink: /projects/zombie-map/
description: A tutorial on how to build a zombification risk map per IRIS in France using open data from OSM and INSEE.
img: assets/img/image_bat.PNG
importance: 2
category: Mapping
lang: en
---

## Project Description

This code is a tutorial on how to build a **zombification risk map** scored per IRIS in France.

The higher the score, the more dangerous the IRIS:
- The higher the number of cemeteries in the IRIS & the closer to one (×0.35)
- The closer the IRIS is to an airport (×0.20)
- The higher the population density (×0.15)
- The higher the ratio of people aged 75 and above (×0.10)
- The higher the number of disabled people receiving AAH (×0.10)
- The closer to a weapon shop (×0.10)

All you need to do is insert the **INSEE code** of any commune in France and the script will generate a risk map automatically.

## Datasets used

| Dataset | Source |
|---|---|
| Cemetery points & polygons | BDTOPO 2026 |
| Population density | INSEE (base IRIS 2022) |
| 75+ year old ratio | INSEE (base IRIS 2022) |
| Disabled people (AAH recipients) | CAF / INSEE 2021 |
| Airfields & airports | BDTOPO 2026 |
| Weapon shops | OpenStreetMap (OSM) |
| IRIS contours | IGN CONTOURS-IRIS 2022 |

## Libraries used

- geopandas
- pandas
- numpy
- folium
- branca
- scikit-learn

## Preview

<img src="/assets/img/image_bat.PNG" width="100%" style="border-radius: 8px; margin-bottom: 20px;" alt="Application preview">

## Result

<iframe src="/assets/html/zombie_map.html" width="100%" height="500px" style="border:none; border-radius: 8px;"></iframe>

## Interested in reusing the code?

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
    background-color: #ad606b !important;
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: rotateX(360deg);
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://github.com/kalmahj/zombie-map" target="_blank" class="btn-flip">
        <i class="fab fa-github"></i> Get the Code on GitHub
    </a>
</div>
