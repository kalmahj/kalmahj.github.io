---
layout: page
title: Walkability Mapping
permalink: /fr/projects/walkability-mapping/
description: Une analyse de marché d'une ville de votre choix en utilisant uniquement des données ouvertes OSM et des outils géospatiaux.
img: assets/img/walkability_thumbnail.PNG
importance: 1
category: Mapping
lang: fr
--- 

## Description du Projet
Les villes aiment parler de marchabilité (walkability). Mais à quel point une ville est-elle réellement marchable en pratique lorsque la mobilité quotidienne dépend si fortement des transports en commun ?
Ce projet explore cette question en produisant un score spatial de marchabilité basé sur l'accès aux arrêts de transports en commun, en utilisant uniquement des données ouvertes OSM et des outils géospatiaux.

*Ce code a été fortement inspiré par Afagh Zeydani sur Linkedin. Beaucoup de crédit lui revient pour son travail et pour l'avoir partagé avec la communauté.*

## À quoi s'attendre
- Un score de marchabilité dans un carré de votre choix
- Une carte de la ville avec le score de marchabilité + les arrêts de transport
- Une génération automatique de carte folium

## Comment l'utiliser
Mon code est très intuitif. Il vous suffit de modifier le nom du lieu de votre choix au début du code et de l'exécuter !

*Veuillez respecter le format : "Ville, Pays"*

## Exemple
```python
city = "Amsterdam, Netherlands"
```
## Bibliothèques utilisées
- osmnx
- folium
- geopandas
- shapely
- pandas
- utm
- branca

## Résultat
<iframe src="/assets/html/amsterdam_walkability_map.html" width="100%" height="500px" style="border:none;"></iframe>

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
    background-color: #ad606b !important; /* Pink on hover */
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: rotateX(360deg); 
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://github.com/kalmahj/Walkability" target="_blank" class="btn-flip">
        <i class="fab fa-github"></i> Obtenir le code sur GitHub
    </a>
</div>
