---
layout: page
title: Évolution urbaine de Brasilia par télédétection
permalink: /fr/projects/remote_sensing_brazilia/
description: Utilisation d'images ENVI et Landsat
img: assets/img/rs_brazilia_fig5.jpg
importance: 1
category: Articles
lang: fr
---

**HAZARA, Kalma**  
Master Géomatique Appliquée aux études urbaines et aux risques

**EVOLUTION URBAINE DE BRASILIA**

**Cours Master 1 Télédétection**

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/title_image_remote_sensing.png" title="Image titre" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## SOMMAIRE

- [Introduction](#introduction)
- [Méthodologie](#méthodologie)
  - [Cadrer les images sur mon centre d’étude](#cadrer-les-images-sur-mon-centre-détude)
  - [Mettre mes images en fausses couleurs](#mettre-mes-images-en-fausses-couleurs)
  - [Calcul du NDVI](#calcul-du-ndvi)
  - [Outil différence d’image](#outil-différence-dimage)
- [Analyse](#analyse)
  - [Brasilia, une ville qui se densifie](#i-brasilia-une-ville-qui-se-densifie)
  - [Une décentralisation de la ville](#ii-une-décentralisation-de-la-ville)
  - [Brasilia, une ville verte ?](#iii-brasilia-une-ville-verte-)
- [Conclusion](#conclusion)
- [Bibliographie](#bibliographie)

## INTRODUCTION

“Après avoir campé pendant presque deux cents ans au bord de l’eau, le Brésil va prendre possession de son territoire.” (KUBITSCHEK, 1960). Le 21 avril 1960, à 1200 km de São Paulo et de Rio de Janeiro, le président brésilien Juscelino Kubitschek inaugure la nouvelle capitale du Brésil, nommée Brasilia. C’est un exemple urbanistique unique, car elle est une ville relativement récente qui a été créée ex nihilo en moins de trois ans, sur un espace vierge de toute urbanisation. D’un périmètre de 112 km2 et dénommé Plano Piloto, elle fut inscrite sur la liste du patrimoine mondial de l’humanité de l’UNESCO en 1987 pour ses multiples chefs-d'œuvre architecturaux fortement inspirés du style moderne. Elle possède un plan urbain sectoriel des fonctions, séparant l’habitat, le travail et les loisirs avec un peuplement prévu de 500 000 habitants. Aujourd’hui, Brasilia a dépassé les deux millions d’habitants (3,5 millions dans l’aire urbaine), est devenue une métropole de référence dans le réseau urbain brésilien et a une importance internationale. Cette croissance en seulement quelques décennies me semblait donc intéressante pour une détection de changement multi-dates. Ainsi, grâce au logiciel ENVI, j’analyserai 3 images satellitaires de Brasilia afin d’observer les changements urbains qu’a subi cette ville. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing1_p2.png" title="Image satellite de Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing2_p2.png" title="Localisation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Les images sont extraites du site officiel de l’Institut d’études géologiques des Etats-Unis (USGS Earth Explorer), à partir de deux satellites Landsat différents. Voici un tableau détaillant chaque image que j’ai utilisée.

<div style="display: flex; justify-content: center;">

|  | DATE D’ACQUISITION | SATELLITE |
| :---- | ----- | ----- |
| **IMAGE 1** | 01/05/1984 | Landsat 5 |
| **IMAGE 2** | 01/09/2011 | Landsat 5 |
| **IMAGE 3** | 01/05/2024 | Landsat 7 |

</div>

<br>

## METHODOLOGIE

En jouant avec les bandes spectrales et en utilisant les paramètres sur ENVI, j’ai pu générer des images intéressantes qui nous permettront de voir les différences urbanistiques entre les trois dates. Sachant que c’est une ville assez particulière qui suit un plan prédéfini, je tenterai d’analyser à travers les images que j’ai obtenues, la densification et l’étalement urbain de Brasilia depuis les années 1980 jusqu'à aujourd'hui. Voici les méthodes de détection qui me semblaient pertinentes pour mon étude : 

### 1. Cadrer les images sur mon centre d’étude

Sur USGS, les images brutes qui nous sont fournies sont souvent trop grandes que notre périmètre d’étude. Il fallait donc cadrer l’image sur la zone qui m’intéressait, c'est-à-dire sur la ville de Brasilia et ses alentours. J’ai utilisé l’outil ‘Spectral Indice’, car elle nous permet d’augmenter l’échelle, sans réduire la résolution de l’image. La projection que j’ai utilisée suit la logique américaine : WGS 84.

### 2. Mettre mes images en fausses couleurs

En vraies couleurs, distinguer le bâti de l’espace vert était un défi. Ainsi, en jouant avec les bandes aux canaux RGB, j’ai choisi une combinaison qui permet de visualiser les différents éléments de façon plus claire : la fausse couleur. Voici les paramètres que j’ai utilisé pour mes images en fonction de leur type de satellite :  

<div style="display: flex; justify-content: center;">

|  | LANDSAT 5 | LANDSAT 7 |
| :---- | ----- | ----- |
| **Rouge** | Bande 4 (Proche Infrarouge) | Bande 5 (Proche Infrarouge) |
| **Vert** | Bande 3 (Rouge) | Bande 4 (Rouge) |
| **Bleu** | Bande 2  (Vert) | Bande 3 (Vert) |

</div>

<br>

### 3. Calcul du NDVI

L’indice de végétation par différence normalisée, ou NDVI, mesure la verdure et la densité de végétation capturée par l’image satellite. Il est compris entre -1 et 1. La formule est la suivante : 

L’outil que j’utiliserai sur ENVI s’appelle ‘Band Maths’. C’est un outil qui permet d'appliquer une opération mathématique ou une fonction personnalisée à une ou plusieurs bandes d'une image. J’appliquerai cette formule du NDVI pour chacune de mes images. Bien sûr, les bandes utilisées pour le NDVI sont différentes entre satellites. Ainsi, pour les deux premières images de 1984 et 2011, soit des images du Landsat 5, on utilisera la formule suivante :  

<div class="row justify-content-sm-center" style="text-align: center;">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ndvi_calculation.png" title="Calcul NDVI" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**(Bande 4 - Bande 3) / (Bande 4 + Bande 3)**

Pour le Landsat 7, on utilisera la suivante : 

**(Bande 5 - Bande 4) / (Bande 5 + Bande 4)**

### 4. Outil différence d’image

Grâce à l’outil ‘Change Detection Workflow’ sur ENVI, il nous est facile de détecter les changements entre deux dates. Nous allons notamment nous concentrer sur l’option ‘Image Difference’, qui possède comme concept la superposition de l’image ‘après’ sur l’image ‘avant’ et ensuite, une soustraction des pixels pour pouvoir détecter les évolutions au cours du temps. Les applications courantes de cet outil sont les suivantes : surveillance de l'environnement, comme la déforestation ; le développement urbain, comme le nombre de bâtiments ajoutés à une zone commerciale, etc… Ce qui rentre parfaitement dans notre étude.

## ANALYSE

### I/ Brasilia, une ville qui se densifie

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image1.jpg" title="Image 1: Brasilia (1984) en fausses couleurs (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 1: Brasilia (1984) en fausses couleurs (Linear 2%)
</div>

L’image de Brasilia en 1984 en fausses couleurs nous permet d’apprécier les différents éléments de notre zone d’étude. En bleu clair figurent les espaces urbanisés et en rouge sont les espaces verts chlorophylliens. En effet, en ce qui concerne la structure spatiale de Brasilia, Lucio Costa (l’urbaniste a l’origine du plan de cette ville) a divisé l'espace bâti en quatre secteurs : monumental, résidentiel, social et bucolique (voir figure 1). L'architecte n'a pas interdit la mixité des secteurs, mais la distribution appliquée à Brasilia a conduit à la sectorisation des fonctions sur l'ensemble du territoire. La théorie du fonctionnalisme, défendue par Le Corbusier, est sans doute sa plus grande influence. En outre, à Brasilia, les terrains étaient contrôlés par l'État et distribués administrativement, plutôt que vendus sur un marché libre.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig1.jpg" title="Figure 1: Utilisation du sol en zone bâtie dans le District fédéral (2017)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: Utilisation du sol en zone bâtie dans le District fédéral (2017). Source : SEGETH, 2017
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image2.jpg" title="Image 2: Brasilia (2011) en fausses couleurs (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 2: Brasilia (2011) en fausses couleurs (Linear 2%)
</div>

Cette carte (Figure 1), issue d’un article écrit par Cayo Costa et Sugie Lee sur l’évolution urbaine de Brasilia, nous permet d’identifier la sectorisation du territoire par différentes fonctions. Nous observons que l’emprise du sol est dédiée majoritairement au résidentiel. Sur nos images satellites, nous les identifions clairement en tant qu’espaces les plus denses. Il est intéressant d’observer que ces zones résidentielles continuent à se densifier et à s’étendre au cours des années, alors que les autres zones restent “figées”. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image3.jpg" title="Image 3: Brasilia (2024) en fausses couleurs (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 3: Brasilia (2024) en fausses couleurs (Linear 2%). <br>
    <b>Vert</b>: Zone figée (commerciale et institutionnelle). <b>Violet</b>: Zone en constante évolution (résidentiel)
</div>

Ce tableau ci-dessous (Figure 2) nous détaille la hausse constante de la population de Brasilia. Depuis les années 1980 jusqu’en 2015, la population a presque doublé, mais sa densité a étonnamment diminué. Cela nous amène à supposer que Brasilia n’est pas dans une logique de densification, mais plutôt d’étalement urbain. Etant donné que la ville suit la théorie du fonctionnalisme de Le Corbusier, la ville utilise les capacités des automobiles pour s’étendre au-delà de ses limites.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig2.jpg" title="Figure 2: La croissance démographie de Brasilia de 1960 à 2015" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: La croissance démographie de Brasilia de 1960 à 2015. Source : IBGE (Institut Brésilien de géographie et de statistique)
</div>

### II/ Une décentralisation de la ville

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig3.jpg" title="Figure 3: Agglomération urbaine et décentralisation économique" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 3: Agglomération urbaine et décentralisation économique promues par les politiques de développement urbain entre la fin des années 1980 et les années 1990. Source : Costa, Cayo, et Sugi Lee
</div>

La densification de la ville de Brasilia a entraîné au début des années 1980, la création de deux nouvelles villes satellites. Elles ont commencé avec Samambaia (1981) puis, un secteur industriel a été installé (Ceilândia)  pour répondre à la demande d'emplois dans la région, suivi par la construction d'une voie rapide directement reliée à Brasilia. Au cours des années suivantes, afin de répondre à la pénurie de logements, le gouvernement de Brasilia a mis en place la municipalité administrative de Samambaia, puis de Santa Maria, Recanto das Emas, São Sebastião, Paranoá, Riacho Fundo 1 et 2, et Candangolândia. 

En ayant ces informations, je voudrais détecter l’apparition des ces villes satellites en faisant une différence d’image entre 1984 et 2024. Voici ce que j’ai obtenu : 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image4.jpg" title="Image 4: Détection des villes satellites grâce à la différence d’image (1984-2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 4: Détection des villes satellites grâce à la différence d’image (1984-2024)
</div>

Top right : Samambaia
Top left : Taguatinga
Bottom left : Gama

### III/ Brasilia, une ville verte ?

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image5.jpg" title="Image 5: NDVI Brasilia (1984)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 5: NDVI Brasilia (1984)
</div>

A part son aspect futuriste, Brasilia est aussi connue pour sa nature. La ville est située à proximité du parc national de Brasilia au nord de la ville, ayant  une grande superficie de 423,83 km2. Autour de Brasilia et de villes satellites se trouvent des champs cultivés.

Il faut savoir que le NDVI ne détecte pas tous les végétaux mais seulement ceux qui sont chlorophylliens. Ainsi, il dépend de la saison. L’image de 1984 et de 2024 date du mois de mai alors que l’image de 2011 date de septembre. Je n’ai malheureusement pas sélectionné les mêmes mois en raison du manque de bonnes images sur le site USGS. Cependant, selon cette charte climatologique, le climat à Brasilia en mai et en septembre se ressemblent. Donc, une analyse croisée pourrait être pertinente.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig4.jpg" title="Figure 4: Climat habituel à Brasilia dans l’année" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 4: Climat habituel à Brasilia dans l’année
</div>

A travers les années, nous remarquons que certains espaces verts de Brasilia se sont dégradés : ils perdent leur capacité chlorophyllienne. Cela est observable car les espaces verts qui ont une couleur bleu vif en 1984 ont connu une diminution du NDVI sur l’image de 2011 et de 2024. Certains endroits qui ont subi cette diminution sont liés à l’urbanisation. 

Mais en général, Brasilia, malgré l’importance de surface bâtie, a une superficie urbaine verte relativement importante. Sachant que c’est une ville moderne typique qui promeut l’usage des voitures, la ville cherche à implanter de la verdure pour compenser l’artificialisation. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image6.jpg" title="Image 6: NDVI Brasilia (2011)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 6: NDVI Brasilia (2011)
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image7.jpg" title="Image 7: NDVI Brasilia (2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 7: NDVI Brasilia (2024)
</div>

## CONCLUSION

“La construction de Brasilia s’inscrit dans un certain imaginaire brésilien. Ce processus a commencé dans les années 1920 et 1930, il a culminé dans les années 1950. Il cherchait à construire, à travers le gouvernement central, l’État-nation brésilien et, en même temps, à forger une identité nationale” (BASSI, 2023)[^1]. 

Brasilia est un cas d’exemple d’une utopie urbaine. Elle souffre actuellement de nombreuses disparités sociales et économiques et est également secouée par des scandales de corruption. Alors que Brasilia a commencé par un plan pilote pré-défini, limité à 500 000 habitants ; la forte immigration du nord du Brésil entre 1957 et 1958, a provoqué une explosion démographique et les nouvelles villes satellites se sont créées. Malheureusement, cette extension s’accompagne d’habitats informels, et la ville qui se veut futuriste cache une triste réalité.   

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig5.jpg" title="Figure 5: Cartographie de l’évolution urbaine de Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 5: Cartographie de l’évolution urbaine de Brasilia
</div>

## BIBLIOGRAPHIE

AFP, GEO avec. « Comment Brasilia est-elle devenue la capitale du Brésil en 1960 ? » Geo.fr, 21 avril 2022. [https://www.geo.fr/histoire/il-y-a-60-ans-brasilia-devenait-la-capitale-du-bresil-200484](https://www.geo.fr/histoire/il-y-a-60-ans-brasilia-devenait-la-capitale-du-bresil-200484).

Costa, Cayo, et Sugi Lee. « The Evolution of Urban Spatial Structure in Brasília: Focusing on the Role of Urban Development Policies », 17 janvier 2019. [https://www.mdpi.com/2071-1050/11/2/553](https://www.mdpi.com/2071-1050/11/2/553).

Guiral Bassi, Danilo. « Acampamentos, logements ouvriers et habitat informel : des chantiers aux quartiers populaires et villes satellites de Brasilia – pistes méthodologiques pour une histoire de l’urbanisme populaire ». Les Cahiers d’Outre-Mer. Revue de géographie de Bordeaux LXXIII, no 282 (1 juillet 2020): 13-38. [https://doi.org/10.4000/com.11973](https://doi.org/10.4000/com.11973).

Mathieu, Marcia Regina de Andrade, Ana Maria Nogales Vasconcelos, Luiz Fernando Macedo Bessa, et Dominique Couret. « Brasilia, vers un développement urbain partagé ». *Géocarrefour* 90, no 1 (15 novembre 2015): 15-25. [https://doi.org/10.4000/geocarrefour.9675](https://doi.org/10.4000/geocarrefour.9675).

Paulgar, Pauline. « Brasilia, de l’utopie à la réalité urbaine (diaporama) ». Batiactu, 23 avril 2010. [https://www.batiactu.com/edito/brasilia-de-l-utopie-a-la-realite-urbaine--diapora-25855.php](https://www.batiactu.com/edito/brasilia-de-l-utopie-a-la-realite-urbaine--diapora-25855.php).

Universalis, Encyclopædia. « BRASÍLIA ». Encyclopædia Universalis. Consulté le 4 janvier 2025. [https://www.universalis.fr/encyclopedie/brasilia/](https://www.universalis.fr/encyclopedie/brasilia/).  

[^1]:  Danilo Guiral Bassi, « *Acampamentos*, logements ouvriers et habitat informel : des chantiers aux quartiers populaires et villes satellites de Brasilia – pistes méthodologiques pour une histoire de l’urbanisme populaire », *Les Cahiers d’Outre-Mer* [En ligne], 282 | Juillet-Décembre, mis en ligne le 01 janvier 2023, consulté le 03 janvier 2025. URL : http://journals.openedition.org/com/11973 ; DOI : https://doi.org/10.4000/com.11973

<!-- PDF Download Button -->
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
    background-color: #ad606b !important;
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: scale(1.05); 
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 50px; margin-bottom: 40px;">
    <h3>Télécharger l'article complet</h3>
    <a href="/assets/pdf/M1GAEUR_Rendu_Teledetection_HAZARA_Kalma.pdf" target="_blank" class="btn-zoom">
        <i class="fas fa-file-pdf"></i> Télécharger l'article original - PDF
    </a>
</div>