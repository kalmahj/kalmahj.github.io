---
layout: page
title: Cartographie du Risque de Zombification
permalink: /fr/projects/zombie-map/
description: Un tutoriel pour construire une carte de risque de zombification par IRIS en France à partir de données ouvertes OSM et INSEE.
img: assets/img/image_bat.PNG
importance: 2
category: Cartographie
lang: fr
---

## Description du Projet

Ce code est un tutoriel sur comment construire une **carte de risque de zombification** scorée par IRIS en France.

Plus le score est élevé, plus l'IRIS est dangereux :
- 🪦 Plus le nombre de cimetières dans l'IRIS est élevé & plus il est proche d'un cimetière (×0.35)
- ✈️ Plus l'IRIS est proche d'un aéroport (×0.20)
- 👥 Plus la densité de population est élevée (×0.15)
- 👴 Plus le ratio de personnes âgées de 75 ans et plus est élevé (×0.10)
- ♿ Plus le nombre de personnes handicapées bénéficiant de l'AAH est élevé (×0.10)
- 🔫 Plus l'IRIS est proche d'un magasin d'armes (×0.10)

Il suffit d'insérer le **code INSEE** de n'importe quelle commune en France et le script génère automatiquement une carte de risque.

## Données utilisées

| Jeu de données | Source |
|---|---|
| Points et polygones de cimetières | BDTOPO 2026 |
| Densité de population | INSEE (base IRIS 2022) |
| Ratio des 75 ans et plus | INSEE (base IRIS 2022) |
| Personnes handicapées (allocataires AAH) | CAF / INSEE 2021 |
| Aérodromes et aéroports | BDTOPO 2026 |
| Magasins d'armes | OpenStreetMap (OSM) |
| Contours IRIS | IGN CONTOURS-IRIS 2022 |

## Bibliothèques utilisées

- geopandas
- pandas
- numpy
- folium
- branca
- scikit-learn

## Aperçu de l'application

<img src="/assets/img/image_bat.PNG" width="100%" style="border-radius: 8px; margin-bottom: 20px;" alt="Aperçu de l'application">

## Résultat

<iframe src="/assets/html/zombie_map.html" width="100%" height="500px" style="border:none; border-radius: 8px;"></iframe>

## Intéressé par la réutilisation du code ?

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
        <i class="fab fa-github"></i> Obtenir le code sur GitHub
    </a>
</div>
