---
layout: project
title: Electoral GIS during the European Elections 2024
permalink: /projects/electory_gis/
description: Revealing electoral realities through mapping during the European Elections 2024
img: assets/img/electory_gis.jpg
importance: 1
category: Mapping
lang: en
---

## Context
The European Elections 2024 are a crucial moment for democracy in Europe. The Right Wing Party is gaining momentum and it is important to understand what the statistics really say.

Here is a map of the electoral results for the Right Wing Party during the European Elections 2024, revealing certain political realities that maps on the news don't normally show. 

## Data & tools used
- European Elections 2024 Dataset from the French Government
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
    <a href="https://www.data.gouv.fr/pages/donnees-des-elections" target="_blank" class="btn-zoom">
        Click here to access the European Elections 2024 Dataset
    </a>
</div>

- QGIS for Mapping
- Inkscape for aesthetic touch



## Result 
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/electory_gis.jpg" title="Map of electoral results for the Right Wing Party" class="img-fluid rounded z-depth-1" %}
    </div>
</div>