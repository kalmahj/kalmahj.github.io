---
layout: page
title: Modélisation de bâtiments 3D
permalink: /fr/projects/3d-building-modelling/
description: Un modèle de bâtiment 3D multipatch créé à l'aide de points LiDar et d'outils de géotraitement ArcGIS.
img: assets/img/lidar_thumbnail.PNG
importance: 1
category: Cartographie
lang: fr
---

## Description du Projet
Les données LiDar sont un outil puissant pour créer des modèles 3D d'objets. Dans ce projet, j'ai utilisé des données LiDar et des outils de géotraitement ArcGIS pour créer un modèle 3D multipatch de Gulpen, aux Pays-Bas, en utilisant ArcGIS Pro.

## Qu'est-ce que les données Lidar ?
La détection et télémétrie par la lumière (lidar) est une technologie utilisée pour créer des modèles haute résolution de l'élévation du sol avec une précision verticale de 10 centimètres (4 pouces). L'équipement Lidar, qui comprend un scanner laser, un système de positionnement global (GPS) et un système de navigation inertielle (INS), est généralement monté sur un petit avion.

Le scanner laser transmet de brèves impulsions lumineuses vers la surface du sol. **Ces impulsions sont réfléchies ou diffusées, et leur temps de trajet est utilisé pour calculer la distance entre le scanner laser et le sol.**

Les données Lidar sont initialement collectées sous forme de "nuage de points" de points individuels réfléchis par tout ce qui se trouve à la surface, y compris les structures et la végétation. Pour produire un modèle numérique d'élévation (MNE) "sol nu", les structures et la végétation sont supprimées (USGS, 2022).

Par exemple, les voitures modernes utilisent les données LiDar pour naviguer dans les villes ou détecter des obstacles soudains sur la route qu'une caméra normale ne peut pas voir.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/lidar.jpg" title="Exemple de données Lidar" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Comment obtenir des données Lidar ?
Si vous êtes aux États-Unis, vous pouvez accéder aux données Lidar auprès de l'USGS (US Geological Survey).
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
        Cliquez ici pour accéder aux données Lidar des États-Unis
    </a>
</div>

Si vous êtes en France, je vous recommande vivement d'utiliser le Lidar 3D de l'IGN (Institut Géographique National). C'est un service gratuit fourni par le gouvernement français.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://geoservices.ign.fr/lidarhd" target="_blank" class="btn-zoom">
        Cliquez ici pour accéder aux données Lidar françaises
    </a>
</div>

Si vous êtes aux Pays-Bas, je vous recommande vivement d'utiliser le Lidar 3D de l'Actueel Hoogstebestand Nederland (AHN). C'est un service gratuit fourni par le gouvernement néerlandais.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.ahn.nl/dataroom" target="_blank" class="btn-zoom">
        Cliquez ici pour accéder aux données Lidar néerlandaises
    </a>
</div>

## Résultat 
<video width="100%" controls>
  <source src="/assets/img/3d_arcgis.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la balise vidéo.
</video>

## Intéressé par le tutoriel ?

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://learn.arcgis.com/fr/projects/extract-3d-buildings-from-lidar-data/" target="_blank" class="btn-zoom">
        Cliquez ici pour accéder au tutoriel
    </a>
</div>
