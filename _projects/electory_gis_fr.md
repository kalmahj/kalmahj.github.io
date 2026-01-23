---
layout: page
title: SIG électoral lors des élections européennes 2024
permalink: /fr/projects/electory_gis/
description: Révéler les réalités électorales par la cartographie lors des élections européennes 2024
img: assets/img/electory_gis.jpg
importance: 1
category: Cartographie
lang: fr
---

## Contexte
Les élections européennes de 2024 sont un moment crucial pour la démocratie en Europe. Le parti de droite gagne du terrain et il est important de comprendre ce que disent vraiment les statistiques.

Voici une carte des résultats électoraux pour le parti de droite lors des élections européennes de 2024, révélant certaines réalités politiques que les cartes aux informations ne montrent pas normalement. 

Ci-dessous, vous pouvez lire l'analyse infographique complète.

<!-- CSS for Standard Content -->
<style>
.text-content {
    padding: 20px;
    border-radius: 8px;
    background-color: #f8f9fa;
    border-left: 5px solid #539eac;
    margin-bottom: 2rem;
}

/* Dark Mode Adjustments */
body.dark-theme .text-content {
    background-color: #2c2c2c;
    color: #e0e0e0;
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

## Données et outils utilisés
- Dataset des élections européennes 2024 du gouvernement français

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.data.gouv.fr/pages/donnees-des-elections" target="_blank" class="btn-zoom">
        Cliquez ici pour accéder au jeu de données des élections européennes 2024
    </a>
</div>

- QGIS pour la cartographie
- Inkscape pour la touche esthétique

## Analyse Infographique

<div class="row mt-5">
    <div class="col-md-7">
        {% include figure.html path="assets/img/electory_gis.jpg" title="Infographie d'analyse électorale" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-5">
        <div class="text-content">
            <h4>Le Rassemblement National était-il vraiment en tête des élections ?</h4>
            <p>Une carte de Nicolas Lambert et Françoise Bahoken a témoigné une victoire exagérée du RN lors des élections européenes. Beaucoup se demande de la fiabilité de leur carte, à l'égard du manque d'informations statistiques. Ainsi, à partir des bases de données officielles (data.gouv), nous allons tenter de démontrer une cartographie électorale plus réaliste.</p>
        </div>

        <div class="text-content">
            <p><strong>Légende 1 :</strong> Nombre de votes RN</p>
            <p><strong>Légende 2 :</strong> % de votes RN</p>
        </div>

        <div class="text-content">
            <h4>Analyse</h4>
            <p>Un pourcentage élevé dans les petites villes, où le poids démographique est faible !</p>
            <p>Seulement 74 cantons sur 1906 avait une majorité absolue des RN.</p>
            <p>Beaucoup d'abstentions. La valeur maximale de la part des votes exprimés ne dépassent pas 65% !</p>
        </div>
    </div>
</div>

## Principales conclusions

L'analyse révèle des nuances importantes dans l'interprétation électorale :

1. **Contexte démographique** : Les pourcentages les plus élevés du RN apparaissent dans les zones à faible poids démographique.
2. **Majorité absolue limitée** : Seuls 74 cantons sur 1906 ont montré une majorité absolue du RN.
3. **Taux d'abstention élevé** : La part maximale des votes exprimés reste inférieure à 65%.

Cela démontre l'importance de contextualiser les cartes électorales avec des informations statistiques appropriées pour éviter des représentations trompeuses de la réalité électorale.
