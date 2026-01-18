---
layout: page
title: Verkiezings-GIS tijdens de Europese Verkiezingen 2024
permalink: /nl/projects/electory_gis/
description: Electorale realiteiten onthullen door middel van mapping tijdens de Europese Verkiezingen 2024
img: assets/img/electory_gis.jpg
importance: 1
category: Mapping
lang: nl
---

## Context
De Europese Verkiezingen 2024 zijn een cruciaal moment voor de democratie in Europa. De Rechtse Partij wint aan momentum en het is belangrijk om te begrijpen wat de statistieken werkelijk zeggen.

Hier is een kaart van de electorale resultaten voor de Rechtse Partij tijdens de Europese Verkiezingen 2024, die bepaalde politieke realiteiten onthult die kaarten op het nieuws normaal niet tonen. 

Hieronder kunt u de volledige infografische analyse lezen met interactieve vertaling. **Beweeg over de Franse tekst om de Nederlandse versie te zien!**

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

## Gegevens & tools gebruikt
- Dataset Europese Verkiezingen 2024 van de Franse Overheid

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.data.gouv.fr/pages/donnees-des-elections" target="_blank" class="btn-zoom">
        Klik hier voor toegang tot de Dataset Europese Verkiezingen 2024
    </a>
</div>

- QGIS voor Mapping
- Inkscape voor esthetische touch

## Infografische Analyse

<div class="row mt-5">
    <div class="col-md-7">
        {% include figure.html path="assets/img/electory_gis.jpg" title="Electorale analyse infographic" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-5">
        <div class="translation-container">
            <div class="text-content text-original">
                <h4>Le Rassemblement National était-il vraiment en tête des élections ?</h4>
                <p>Une carte de Nicolas Lambert et Françoise Bahoken a témoigné une victoire exagérée du RN lors des élections européenes. Beaucoup se demande de la fiabilité de leur carte, à l'égard du manque d'informations statistiques. Ainsi, à partir des bases de données officielles (data.gouv), nous allons tenter de démontrer une cartographie électorale plus réaliste.</p>
            </div>
            <div class="text-content text-translated">
                <h4>Was het National Rally echt aan de leiding bij de verkiezingen?</h4>
                <p>Een kaart van Nicolas Lambert en Françoise Bahoken toonde een overdreven overwinning van het RN tijdens de Europese verkiezingen. Velen twijfelen aan de betrouwbaarheid van hun kaart, gezien het gebrek aan statistische informatie. Zo zullen we, met behulp van officiële databanken (data.gouv), proberen een meer realistische electorale cartografie aan te tonen.</p>
            </div>
        </div>

        <div class="translation-container">
            <div class="text-content text-original">
                <p><strong>Légende 1 :</strong> Nombre de votes RN</p>
                <p><strong>Légende 2 :</strong> % de votes RN</p>
            </div>
            <div class="text-content text-translated">
                <p><strong>Legende 1:</strong> Aantal RN-stemmen</p>
                <p><strong>Legende 2:</strong> % RN-stemmen</p>
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
                <h4>Analyse</h4>
                <p>Een hoog percentage in kleine steden, waar het demografisch gewicht laag is! </p>
                <p>Slechts 74 kantons van de 1906 hadden een absolute meerderheid van RN-stemmen.</p>
                <p>Veel onthoudingen. De maximale waarde van het aandeel uitgebrachte stemmen is niet hoger dan 65%!</p>
            </div>
        </div>
    </div>
</div>

## Belangrijkste Bevindingen

De analyse onthult belangrijke nuances in de electorale interpretatie:

1. **Demografische Context**: De hoogste RN-percentages verschijnen in gebieden met een laag demografisch gewicht
2. **Beperkte Absolute Meerderheid**: Slechts 74 van de 1906 kantons toonden een absolute RN-meerderheid
3. **Hoog Percentage Onthoudingen**: Het maximale aandeel uitgebrachte stemmen blijft onder de 65%

Dit toont het belang aan van het contextualiseren van electorale kaarten met de juiste statistische informatie om misleidende voorstellingen van de electorale realiteit te voorkomen.
