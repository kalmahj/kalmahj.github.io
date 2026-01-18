---
layout: page
title: Loopbaarheid in Kaart Brengen
permalink: /nl/projects/walkability-mapping/
description: Een loopbaarheidsanalyse van een stad naar keuze met alleen OSM open data en geospatiale tools.
img: assets/img/walkability_thumbnail.PNG
importance: 1
category: Mapping
lang: nl
--- 

## Projectbeschrijving
Steden praten graag over loopbaarheid. Maar hoe loopbaar is een stad in de praktijk als de dagelijkse mobiliteit zo sterk afhankelijk is van het openbaar vervoer?
Dit project onderzoekt die vraag door een ruimtelijke loopbaarheidsscore te produceren op basis van toegang tot haltes van het openbaar vervoer, met behulp van alleen OSM open data en geospatiale tools.

*Deze code is zwaar geïnspireerd door Afagh Zeydani op Linkedin. Veel eer gaat naar hem voor zijn werk en voor het delen ervan met de gemeenschap.*

## Wat u kunt verwachten
- Een loopbaarheidsscore in een vak van een vierkante meter naar keuze
- Een kaart van de stad met de loopbaarheidsscore + transporthaltes
- Een automatische folium kaart generatie

## Hoe te gebruiken
Mijn code is zeer intuïtief. Het enige wat u hoeft te doen is de locatienaam van uw keuze aan het begin van de code te wijzigen en deze uit te voeren!

*Respecteer het formaat : "Stad, Land"*

## Voorbeeld
```python
city = "Amsterdam, Netherlands"
```
## Gebruikte bibliotheken
- osmnx
- folium
- geopandas
- shapely
- pandas
- utm
- branca

## Resultaat
<iframe src="/assets/html/amsterdam_walkability_map.html" width="100%" height="500px" style="border:none;"></iframe>

## Geïnteresseerd in het hergebruiken van de code?

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
        <i class="fab fa-github"></i> Haal de code op GitHub
    </a>
</div>
