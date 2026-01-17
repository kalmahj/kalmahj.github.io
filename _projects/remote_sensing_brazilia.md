---
layout: page
title: Tracking Brasilia's Urban Evolution through Remote Sensing
permalink: /projects/remote_sensing_brazilia/
description: Usage of ENVI and Landsat images
img: assets/img/rs_brazilia_fig5.jpg
importance: 1
category: Articles
lang: en
---

**HAZARA, Kalma**  
Master in Applied Geomatics for Urban Studies and Risks

**URBAN EVOLUTION OF BRASILIA**

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/title_image_remote_sensing.png" title="Title image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## TABLE OF CONTENTS

- [Introduction](#introduction)
- [Methodology](#methodology)
  - [Cropping images to my study center](#cropping-images-to-my-study-center)
  - [Setting my images to false colors](#setting-my-images-to-false-colors)
  - [NDVI Calculation](#ndvi-calculation)
  - [Image Difference Tool](#image-difference-tool)
- [Analysis](#analysis)
  - [Brasilia, a densifying city](#i-brasilia-a-densifying-city)
  - [A decentralization of the city](#ii-a-decentralization-of-the-city)
  - [Brasilia, a green city?](#iii-brasilia-a-green-city)
- [Conclusion](#conclusion)
- [Bibliography](#bibliography)

## INTRODUCTION

“After camping for almost two hundred years by the water, Brazil is going to take possession of its territory.” (KUBITSCHEK, 1960). On April 21, 1960, 1200 km from São Paulo and Rio de Janeiro, Brazilian President Juscelino Kubitschek inaugurated the new capital of Brazil, named Brasilia. It is a unique urban planning example, as it is a relatively recent city created ex nihilo in less than three years, on a virgin space void of any urbanization. With a perimeter of 112 km² and named Plano Piloto, it was inscribed on the UNESCO World Heritage List in 1987 for its multiple architectural masterpieces heavily inspired by the modern style. It possesses a sectoral urban plan of functions, separating housing, work, and leisure with a planned population of 500,000 inhabitants. Today, Brasilia has exceeded two million inhabitants (3.5 million in the urban area), has become a reference metropolis in the Brazilian urban network, and has international importance. This growth in only a few decades therefore seemed interesting to me for a multi-date change detection. Thus, thanks to the ENVI software, I will analyze 3 satellite images of Brasilia in order to observe the urban changes this city has undergone. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing1_p2.png" title="Satellite image of Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing2_p2.png" title="Location" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The images are extracted from the official website of the United States Geological Survey (USGS Earth Explorer), from two different Landsat satellites. Here is a table detailing each image I used.

<div style="display: flex; justify-content: center;">

|  | ACQUISITION DATE | SATELLITE |
| :---- | ----- | ----- |
| **IMAGE 1** | 01/05/1984 | Landsat 5 |
| **IMAGE 2** | 01/09/2011 | Landsat 5 |
| **IMAGE 3** | 01/05/2024 | Landsat 7 |

</div>

<br>

## METHODOLOGY

By playing with the spectral bands and using the parameters on ENVI, I was able to generate interesting images that will allow us to see the urbanistic differences between the three dates. Knowing that it is a quite particular city that follows a predefined plan, I will attempt to analyze, through the images I obtained, the densification and urban sprawl of Brasilia from the 1980s until today. Here are the detection methods that seemed relevant for my study: 

### 1. Cropping images to my study center

On USGS, the raw images provided to us are often larger than our study perimeter. It was therefore necessary to crop the image to the zone that interested me, that is to say, on the city of Brasilia and its surroundings. I used the ‘Spectral Indice’ tool, because it allows us to increase the scale, without reducing the resolution of the image. The projection I used follows the American logic: WGS 84.

### 2. Setting my images to false colors

In true colors, distinguishing buildings from green space was a challenge. Thus, by playing with the bands in the RGB channels, I chose a combination that allows visualizing the different elements more clearly: false color. Here are the parameters I used for my images depending on their satellite type:  

<div style="display: flex; justify-content: center;">

|  | LANDSAT 5 | LANDSAT 7 |
| :---- | ----- | ----- |
| **Red** | Band 4 (Near Infrared) | Band 5 (Near Infrared) |
| **Green** | Band 3 (Red) | Band 4 (Red) |
| **Blue** | Band 2  (Green) | Band 3 (Green) |

</div>

<br>

### 3. NDVI Calculation

The Normalized Difference Vegetation Index, or NDVI, measures the greenery and density of vegetation captured by the satellite image. It ranges between -1 and 1. The tool I will use on ENVI is called ‘Band Maths’. It is a tool that allows applying a mathematical operation or a custom function to one or more bands of an image. I will apply this NDVI formula for each of my images :

<div class="row justify-content-sm-center" style="text-align: center;">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ndvi_calculation.png" title="NDVI calculation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Of course, the bands used for NDVI are different between satellites. Thus, for the first two images from 1984 and 2011, which are Landsat 5 images, we will use the following formula:  

**(Band 4 - Band 3) / (Band 4 + Band 3)**

For Landsat 7, we will use the following: 

**(Band 5 - Band 4) / (Band 5 + Band 4)**

### 4. Image Difference Tool

Thanks to the ‘Change Detection Workflow’ tool on ENVI, it is easy for us to detect changes between two dates. We will notably focus on the ‘Image Difference’ option, which has as a concept the superposition of the ‘after’ image on the ‘before’ image and then, a subtraction of pixels to be able to detect evolutions over time. The common applications of this tool are as follows: environmental monitoring, such as deforestation; urban development, such as the number of buildings added to a commercial zone, etc… Which fits perfectly into our study.

## ANALYSIS

### I/ Brasilia, a densifying city

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image1.jpg" title="Image 1: Brasilia (1984) in false colors (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 1: Brasilia (1984) in false colors (Linear 2%)
</div>

The image of Brasilia in 1984 in false colors allows us to appreciate the different elements of our study zone. In light blue are the urbanized spaces and in red are the chlorophyllian green spaces. Indeed, concerning the spatial structure of Brasilia, Lucio Costa (the urban planner behind the city's plan) divided the built space into four sectors: monumental, residential, social, and bucolic (see figure 1). The architect did not forbid the mix of sectors, but the distribution applied to Brasilia led to the sectorization of functions over the entire territory. The theory of functionalism, defended by Le Corbusier, is undoubtedly his greatest influence. Furthermore, in Brasilia, lands were controlled by the State and distributed administratively, rather than sold on a free market.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig1.jpg" title="Figure 1: Land use in built-up areas in the Federal District (2017)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: Land use in built-up areas in the Federal District (2017). Source: SEGETH, 2017
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image2.jpg" title="Image 2: Brasilia (2011) in false colors (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 2: Brasilia (2011) in false colors (Linear 2%)
</div>

This map (Figure 1), from an article written by Cayo Costa and Sugie Lee on the urban evolution of Brasilia, allows us to identify the sectorization of the territory by different functions. We observe that land use is dedicated mainly to residential. On our satellite images, we clearly identify them as the densest spaces. It is interesting to observe that these residential zones continue to densify and expand over the years, while the other zones remain “frozen”. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image3.jpg" title="Image 3: Brasilia (2024) in false colors (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 3: Brasilia (2024) in false colors (Linear 2%). <br>
	<b>Green</b>: Frozen zone (commercial and institutional). <b>Purple</b>: Zone in constant evolution (residential)
</div>

This table below (Figure 2) details the constant rise in Brasilia's population. From the 1980s until 2015, the population almost doubled, but its density surprisingly decreased. This leads us to suppose that Brasilia is not in a logic of densification, but rather of urban sprawl. Given that the city follows Le Corbusier's theory of functionalism, the city uses the capabilities of automobiles to expand beyond its limits.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig2.jpg" title="Figure 2: Demographic growth of Brasilia from 1960 to 2015" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: Demographic growth of Brasilia from 1960 to 2015. Source: IBGE (Brazilian Institute of Geography and Statistics)
</div>

### II/ A decentralization of the city

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig3.jpg" title="Figure 3: Urban agglomeration and economic decentralization promoted by urban development policies between the late 1980s and the 1990s" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 3: Urban agglomeration and economic decentralization promoted by urban development policies between the late 1980s and the 1990s. Source: Costa, Cayo, and Sugi Lee
</div>

The densification of the city of Brasilia led, at the beginning of the 1980s, to the creation of two new satellite cities. They started with Samambaia (1981) then, an industrial sector was installed (Ceilândia) to meet the demand for jobs in the region, followed by the construction of a fast lane directly connected to Brasilia. Over the following years, to respond to the housing shortage, the government of Brasilia set up the administrative municipality of Samambaia, then Santa Maria, Recanto das Emas, São Sebastião, Paranoá, Riacho Fundo 1 and 2, and Candangolândia. 

Having this information, I wanted to detect the appearance of these satellite cities by doing an image difference between 1984 and 2024. Here is what I obtained: 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image4.jpg" title="Image 4: Detection of satellite cities using image difference (1984-2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 4: Detection of satellite cities using image difference (1984-2024)
</div>

Top right : Samambaia
Top left : Taguatinga
Bottom left : Gama

### III/ Brasilia, a green city?

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image5.jpg" title="Image 5: NDVI Brasilia (1984)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image 5: NDVI Brasilia (1984)
</div>

Apart from its futuristic aspect, Brasilia is also known for its nature. The city is located near the Brasilia National Park north of the city, having a large area of 423.83 km². Around Brasilia and satellite cities are cultivated fields.

It should be noted that NDVI does not detect all plants but only those that are chlorophyllian. Thus, it depends on the season. The image from 1984 and 2024 dates from the month of May whereas the image from 2011 dates from September. I unfortunately did not select the same months due to the lack of good images on the USGS site. However, according to this climatological chart, the climate in Brasilia in May and in September is similar. Therefore, a cross-analysis could be relevant.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig4.jpg" title="Figure 4: Usual climate in Brasilia throughout the year" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 4: Usual climate in Brasilia throughout the year
</div>

Throughout the years, we notice that certain green spaces of Brasilia have degraded: they are losing their chlorophyllian capacity. This is observable because the green spaces that have a bright blue color in 1984 experienced a decrease in NDVI on the image of 2011 and 2024. Some places that have undergone this decrease are linked to urbanization. 

But in general, Brasilia, despite the importance of built surface, has a relatively important green urban area. Knowing that it is a typical modern city that promotes the use of cars, the city seeks to implant greenery to compensate for artificialization. 

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

“The construction of Brasilia is part of a certain Brazilian imaginary. This process began in the 1920s and 1930s, it culminated in the 1950s. It sought to build, through the central government, the Brazilian Nation-State and, at the same time, to forge a national identity” (BASSI, 2023)[^1]. 

Brasilia is a case example of an urban utopia. It currently suffers from numerous social and economic disparities and is also shaken by corruption scandals. While Brasilia started with a pre-defined pilot plan, limited to 500,000 inhabitants; the strong immigration from northern Brazil between 1957 and 1958, caused a demographic explosion and new satellite cities were created. Unfortunately, this extension is accompanied by informal settlements, and the city that wants to be futuristic hides a sad reality.   

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig5.jpg" title="Figure 5: Mapping of the urban evolution of Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 5: Mapping of the urban evolution of Brasilia
</div>

## BIBLIOGRAPHY

AFP, GEO with. « Comment Brasilia est-elle devenue la capitale du Brésil en 1960 ? » Geo.fr, April 21, 2022. [https://www.geo.fr/histoire/il-y-a-60-ans-brasilia-devenait-la-capitale-du-bresil-200484](https://www.geo.fr/histoire/il-y-a-60-ans-brasilia-devenait-la-capitale-du-bresil-200484).

Costa, Cayo, and Sugi Lee. « The Evolution of Urban Spatial Structure in Brasília: Focusing on the Role of Urban Development Policies », January 17, 2019. [https://www.mdpi.com/2071-1050/11/2/553](https://www.mdpi.com/2071-1050/11/2/553).

Guiral Bassi, Danilo. « Acampamentos, logements ouvriers et habitat informel : des chantiers aux quartiers populaires et villes satellites de Brasilia – pistes méthodologiques pour une histoire de l’urbanisme populaire ». Les Cahiers d’Outre-Mer. Revue de géographie de Bordeaux LXXIII, no 282 (July 1, 2020): 13-38. [https://doi.org/10.4000/com.11973](https://doi.org/10.4000/com.11973).

Mathieu, Marcia Regina de Andrade, Ana Maria Nogales Vasconcelos, Luiz Fernando Macedo Bessa, and Dominique Couret. « Brasilia, vers un développement urbain partagé ». *Géocarrefour* 90, no 1 (November 15, 2015): 15-25. [https://doi.org/10.4000/geocarrefour.9675](https://doi.org/10.4000/geocarrefour.9675).

Paulgar, Pauline. « Brasilia, de l’utopie à la réalité urbaine (diaporama) ». Batiactu, April 23, 2010. [https://www.batiactu.com/edito/brasilia-de-l-utopie-a-la-realite-urbaine--diapora-25855.php](https://www.batiactu.com/edito/brasilia-de-l-utopie-a-la-realite-urbaine--diapora-25855.php).

Universalis, Encyclopædia. « BRASÍLIA ». Encyclopædia Universalis. Accessed on January 4, 2025. [https://www.universalis.fr/encyclopedie/brasilia/](https://www.universalis.fr/encyclopedie/brasilia/).  

[^1]:  Danilo Guiral Bassi, « *Acampamentos*, logements ouvriers et habitat informel : des chantiers aux quartiers populaires et villes satellites de Brasilia – pistes méthodologiques pour une histoire de l’urbanisme populaire », *Les Cahiers d’Outre-Mer* [Online], 282 | July-December, published online on January 01, 2023, accessed on January 03, 2025. URL : http://journals.openedition.org/com/11973 ; DOI : https://doi.org/10.4000/com.11973

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
    <h3>Download the Full Article</h3>
    <a href="/assets/pdf/M1GAEUR_Rendu_Teledetection_HAZARA_Kalma.pdf" target="_blank" class="btn-zoom">
        <i class="fas fa-file-pdf"></i> Download Original Article - PDF
    </a>
</div>
