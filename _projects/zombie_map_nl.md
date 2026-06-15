---
layout: page
title: Zombificatierisico in Kaart Brengen
permalink: /nl/projects/zombie-map/
description: Een tutorial voor het bouwen van een zombificatierisicokaart per IRIS in Frankrijk met open data van OSM en INSEE.
img: assets/img/image_bat.PNG
importance: 2
category: Mapping
lang: nl
---

## Projectbeschrijving

Deze code is een tutorial over hoe je een **zombificatierisicokaart** opbouwt per IRIS in Frankrijk.

Hoe hoger de score, hoe gevaarlijker de IRIS:
- 🪦 Hoe meer begraafplaatsen in de IRIS & hoe dichter bij een begraafplaats (×0.35)
- ✈️ Hoe dichter de IRIS bij een luchthaven ligt (×0.20)
- 👥 Hoe hoger de bevolkingsdichtheid (×0.15)
- 👴 Hoe hoger het aandeel personen van 75 jaar en ouder (×0.10)
- ♿ Hoe hoger het aantal gehandicapten met een AAH-uitkering (×0.10)
- 🔫 Hoe dichter bij een wapenwinkel (×0.10)

Het enige wat u hoeft te doen is de **INSEE-code** van een willekeurige gemeente in Frankrijk invoeren, waarna het script automatisch een risicokaart genereert.

## Gebruikte datasets

| Dataset | Bron |
|---|---|
| Begraafplaatspunten en -polygonen | BDTOPO 2026 |
| Bevolkingsdichtheid | INSEE (IRIS-basis 2022) |
| Aandeel 75+ jaar | INSEE (IRIS-basis 2022) |
| Gehandicapten (AAH-uitkeringsontvangers) | CAF / INSEE 2021 |
| Vliegvelden en luchthavens | BDTOPO 2026 |
| Wapenwinkels | OpenStreetMap (OSM) |
| IRIS-grenzen | IGN CONTOURS-IRIS 2022 |

## Gebruikte bibliotheken

- geopandas
- pandas
- numpy
- folium
- branca
- scikit-learn

## Voorvertoning van de applicatie

<img src="/assets/img/image_bat.PNG" width="100%" style="border-radius: 8px; margin-bottom: 20px;" alt="Voorvertoning applicatie">

## Resultaat

<iframe src="/assets/html/zombie_map.html" width="100%" height="500px" style="border:none; border-radius: 8px;"></iframe>

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
    background-color: #ad606b !important;
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: rotateX(360deg);
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://github.com/kalmahj/zombie-map" target="_blank" class="btn-flip">
        <i class="fab fa-github"></i> Haal de code op GitHub
    </a>
</div>
