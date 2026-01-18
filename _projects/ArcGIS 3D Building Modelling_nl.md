---
layout: page
title: 3D Gebouwmodellering
permalink: /nl/projects/3d-building-modelling/
description: Een 3D-gebouwmodel (multipatch) gemaakt met LiDar-punten en ArcGIS-geoprocessingtools.
img: assets/img/lidar_thumbnail.PNG
importance: 1
category: Mapping
lang: nl
---

## Projectbeschrijving
LiDar-data is een krachtig hulpmiddel voor het maken van 3D-modellen van objecten. In dit project heb ik LiDar-data en ArcGIS-geoprocessingtools gebruikt om een multipatch 3D-model te maken van Gulpen, Nederland, met behulp van ArcGIS Pro.

## Wat is Lidar-data?
Light Detection and Ranging (lidar) is een technologie die wordt gebruikt om hoge-resolutie modellen van bodemhoogte te maken met een verticale nauwkeurigheid van 10 centimeter (4 inch). Lidar-apparatuur, waaronder een laserscanner, een Global Positioning System (GPS) en een Inertial Navigation System (INS), wordt meestal op een klein vliegtuig gemonteerd.

De laserscanner zendt korte lichtpulsen uit naar het grondoppervlak. **Deze pulsen worden gereflecteerd of verstrooid en hun reistijd wordt gebruikt om de afstand tussen de laserscanner en de grond te berekenen**

Lidar-data wordt in eerste instantie verzameld als een "puntenwolk" (point cloud) van individuele punten die worden gereflecteerd door alles op het oppervlak, inclusief gebouwen en vegetatie. Om een "kale grond" (bare earth) Digitaal Hoogtemodel (DEM) te produceren, worden gebouwen en vegetatie verwijderd (USGS, 2022).

Moderne auto's gebruiken bijvoorbeeld LiDar-data om door steden te navigeren of plotselinge obstakels op de weg te detecteren die een normale camera niet kan zien.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/lidar.jpg" title="Voorbeeld van Lidar-data" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Hoe kom ik aan Lidar-data?
Als u zich in de VS bevindt, kunt u toegang krijgen tot Lidar-data van de USGS (US Geological Survey).
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
        Klik hier voor toegang tot Amerikaanse Lidar-data
    </a>
</div>

Als u zich in Frankrijk bevindt, raad ik u ten zeerste aan om de 3D Lidar van IGN (Institut Géographique National) te gebruiken. Dit is een gratis dienst van de Franse overheid.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://geoservices.ign.fr/lidarhd" target="_blank" class="btn-zoom">
        Klik hier voor toegang tot Franse Lidar-data
    </a>
</div>

Als u zich in Nederland bevindt, raad ik u ten zeerste aan om de 3D Lidar van het Actueel Hoogtebestand Nederland (AHN) te gebruiken. Dit is een gratis dienst van de Nederlandse overheid.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.ahn.nl/dataroom" target="_blank" class="btn-zoom">
        Klik hier voor toegang tot Nederlandse Lidar-data
    </a>
</div>

## Resultaat 
<video width="100%" controls>
  <source src="/assets/img/3d_arcgis.mp4" type="video/mp4">
  Uw browser ondersteunt de video-tag niet.
</video>

## Geïnteresseerd in de tutorial?

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://learn.arcgis.com/fr/projects/extract-3d-buildings-from-lidar-data/" target="_blank" class="btn-zoom">
        Klik hier voor toegang tot de tutorial
    </a>
</div>
