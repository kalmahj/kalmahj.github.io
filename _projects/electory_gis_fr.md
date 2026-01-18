---
layout: page
title: Electoral GIS during the European Elections 2024
permalink: /fr/projects/electory_gis/
description: Revealing electoral realities through mapping during the European Elections 2024
img: assets/img/electory_gis.jpg
importance: 1
category: Mapping
lang: fr
---

## Context
The European Elections 2024 are a crucial moment for democracy in Europe. The Right Wing Party is gaining momentum and it is important to understand what the statistics really say.

Here is a map of the electoral results for the Right Wing Party during the European Elections 2024, revealing certain political realities that maps on the news don't normally show. 

Below you can read the full infographic analysis with interactive translation. **Hover over the French text to see the English version!**

<!-- CSS for Hover Translation Effect -->
<style>
.translation-container {
    position: relative;
    margin-bottom: 2rem;
    cursor: help;
}

.text-content {
    padding: 20px;
    border-radius: 8px;
    background-color: #f8f9fa;
    transition: opacity 0.4s ease;
    border-left: 5px solid #539eac;
}

.text-original {
    display: block;
    opacity: 1;
}

.text-translated {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 100%;
    opacity: 0;
    background-color: #fff;
    z-index: 10;
    pointer-events: none;
    overflow-y: auto;
    padding: 20px;
    border-radius: 8px;
    border-left: 5px solid #ad606b;
}

/* Hover Effect */
.translation-container:hover .text-translated {
    opacity: 1;
}

.translation-container:hover .text-original {
    opacity: 0.1;
}

/* Dark Mode Adjustments */
body.dark-theme .text-content {
    background-color: #2c2c2c;
    color: #e0e0e0;
}
body.dark-theme .text-translated {
    background-color: #2c2c2c;
}

/* Button Style */
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
    background-color: #ad606b !important;
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: scale(1.05); 
    color: white !important;
}
</style>

## Data & tools used
- European Elections 2024 Dataset from the French Government

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.data.gouv.fr/pages/donnees-des-elections" target="_blank" class="btn-zoom">
        Click here to access the European Elections 2024 Dataset
    </a>
</div>

- QGIS for Mapping
- Inkscape for aesthetic touch

## Infographic Analysis

<div class="row mt-5">
    <div class="col-md-7">
        {% include figure.html path="assets/img/electory_gis.jpg" title="Electoral analysis infographic" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-5">
        <div class="translation-container">
            <div class="text-content text-original">
                <h4>Le Rassemblement National était-il vraiment en tête des élections ?</h4>
                <p>Une carte de Nicolas Lambert et Françoise Bahoken a témoigné une victoire exagérée du RN lors des élections européenes. Beaucoup se demande de la fiabilité de leur carte, à l'égard du manque d'informations statistiques. Ainsi, à partir des bases de données officielles (data.gouv), nous allons tenter de démontrer une cartographie électorale plus réaliste.</p>
            </div>
            <div class="text-content text-translated">
                <h4>Was the National Rally really in the lead of the elections?</h4>
                <p>A map by Nicolas Lambert and Françoise Bahoken showed an exaggerated victory of the RN during the European elections. Many question the reliability of their map, given the lack of statistical information. Thus, using official databases (data.gouv), we will attempt to demonstrate a more realistic electoral cartography.</p>
            </div>
        </div>

        <div class="translation-container">
            <div class="text-content text-original">
                <p><strong>Légende 1 :</strong> Nombre de votes RN</p>
                <p><strong>Légende 2 :</strong> % de votes RN</p>
            </div>
            <div class="text-content text-translated">
                <p><strong>Legend 1:</strong> Number of RN votes</p>
                <p><strong>Legend 2:</strong> % of RN votes</p>
            </div>
        </div>

        <div class="translation-container">
            <div class="text-content text-original">
                <h4>Analyse</h4>
                <p>Un pourcentage élevé dans les petites villes, où le poids démographique est faible !</p>
                <p>Seulement 74 cantons sur 1906 avait une majorité absolue des RN.</p>
                <p>Beaucoup d'abstentions. La valeur maximale de la part des votes exprimés ne dépassent pas 65% !</p>
            </div>
            <div class="text-content text-translated">
                <h4>Analysis</h4>
                <p>A high percentage in small towns, where the demographic weight is low!</p>
                <p>Only 74 cantons out of 1906 had an absolute majority of RN votes.</p>
                <p>Many abstentions. The maximum value of the share of votes cast does not exceed 65%!</p>
            </div>
        </div>
    </div>
</div>

## Key Findings

The analysis reveals important nuances in electoral interpretation:

1. **Demographic Context**: The highest RN percentages appear in areas with low demographic weight
2. **Limited Absolute Majority**: Only 74 out of 1906 cantons showed an absolute RN majority
3. **High Abstention Rate**: The maximum share of votes cast remains below 65%

This demonstrates the importance of contextualizing electoral maps with proper statistical information to avoid misleading representations of electoral reality.
