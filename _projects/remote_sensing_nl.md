---
layout: page
title: De stedelijke evolutie van Brasilia volgen via teledetectie
permalink: /nl/projects/remote_sensing_brazilia/
description: Gebruik van ENVI en Landsat-beelden
img: assets/img/rs_brazilia_fig5.jpg
importance: 1
category: Artikelen
lang: nl
---

**HAZARA, Kalma**  
Master Toegepaste Geomatica voor Stedelijke Studies en Risico's

**STEDELIJKE EVOLUTIE VAN BRASILIA**

**Cursus Master 1 Teledetectie**

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/title_image_remote_sensing.png" title="Titelafbeelding" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## INHOUDSOPGAVE

- [Inleiding](#inleiding)
- [Methodologie](#methodologie)
  - [De beelden kadreren op mijn studiecentrum](#de-beelden-kadreren-op-mijn-studiecentrum)
  - [Mijn beelden in valse kleuren zetten](#mijn-beelden-in-valse-kleuren-zetten)
  - [Berekening van de NDVI](#berekening-van-de-ndvi)
  - [Tool voor beeldverschil](#tool-voor-beeldverschil)
- [Analyse](#analyse)
  - [Brasilia, een stad die verdicht](#i-brasilia-een-stad-die-verdicht)
  - [Een decentralisatie van de stad](#ii-een-decentralisatie-van-de-stad)
  - [Brasilia, een groene stad?](#iii-brasilia-een-groene-stad)
- [Conclusie](#conclusie)
- [Bibliografie](#bibliografie)

## INLEIDING

"Na bijna tweehonderd jaar aan de waterkant te hebben gekampeerd, gaat Brazilië zijn grondgebied in bezit nemen." (KUBITSCHEK, 1960). Op 21 april 1960, 1200 km van São Paulo en Rio de Janeiro, huldigde de Braziliaanse president Juscelino Kubitschek de nieuwe hoofdstad van Brazilië in, genaamd Brasilia. Het is een uniek stedenbouwkundig voorbeeld, omdat het een relatief nieuwe stad is die in minder dan drie jaar ex nihilo is gecreëerd, op een gebied dat nog niet verstedelijkt was. Met een omtrek van 112 km² en genaamd Plano Piloto, werd het in 1987 op de Werelderfgoedlijst van UNESCO geplaatst vanwege zijn vele architecturale meesterwerken die sterk geïnspireerd zijn door de moderne stijl. Het heeft een functioneel sectoraal stadsplan, dat wonen, werken en vrije tijd scheidt met een geplande bevolking van 500.000 inwoners. Vandaag de dag heeft Brasilia meer dan twee miljoen inwoners (3,5 miljoen in het stedelijk gebied), is het een referentiemetropool geworden in het Braziliaanse stedelijke netwerk en heeft het internationaal belang. Deze groei in slechts enkele decennia leek mij daarom interessant voor een detectie van veranderingen op meerdere data. Zo zal ik dankzij de software ENVI 3 satellietbeelden van Brasilia analyseren om de stedelijke veranderingen te observeren die deze stad heeft ondergaan.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing1_p2.png" title="Satellietbeeld van Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing2_p2.png" title="Locatie" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

De beelden zijn afkomstig van de officiële website van de United States Geological Survey (USGS Earth Explorer), van twee verschillende Landsat-satellieten. Hier is een tabel met details over elk beeld dat ik heb gebruikt.

<div style="display: flex; justify-content: center;">

|  | OVERNAMEDATUM | SATELLIET |
| :---- | ----- | ----- |
| **BEELD 1** | 01/05/1984 | Landsat 5 |
| **BEELD 2** | 01/09/2011 | Landsat 5 |
| **BEELD 3** | 01/05/2024 | Landsat 7 |

</div>

<br>

## METHODOLOGIE

Door te spelen met de spectrale banden en de parameters op ENVI te gebruiken, heb ik interessante beelden kunnen genereren waarmee we de stedenbouwkundige verschillen tussen de drie data kunnen zien. Wetende dat dit een vrij bijzondere stad is die een vooraf bepaald plan volgt, zal ik proberen te analyseren door middel van de beelden die ik heb verkregen, de verdichting en stedelijke uitbreiding van Brasilia van de jaren 1980 tot vandaag. Hier zijn de detectiemethoden die mij relevant leken voor mijn studie:

### 1. De beelden kadreren op mijn studiecentrum

Op USGS zijn de ruwe beelden die ons worden verstrekt vaak te groot voor onze studieperimeter. Het was daarom nodig om het beeld te kadreren op de zone die mij interesseerde, dat wil zeggen op de stad Brasilia en haar omgeving. Ik heb de tool 'Spectral Indice' gebruikt, omdat deze ons in staat stelt de schaal te vergroten, zonder de resolutie van het beeld te verminderen. De projectie die ik heb gebruikt volgt de Amerikaanse logica: WGS 84.

### 2. Mijn beelden in valse kleuren zetten

In echte kleuren was het onderscheiden van gebouwen van groene ruimte een uitdaging. Dus door te spelen met de banden van de RGB-kanalen, heb ik een combinatie gekozen die het mogelijk maakt om de verschillende elementen duidelijker te visualiseren: de valse kleur. Hier zijn de parameters die ik heb gebruikt voor mijn beelden op basis van hun satelliettype:

<div style="display: flex; justify-content: center;">

|  | LANDSAT 5 | LANDSAT 7 |
| :---- | ----- | ----- |
| **Rood** | Band 4 (Nabij-infrarood) | Band 5 (Nabij-infrarood) |
| **Groen** | Band 3 (Rood) | Band 4 (Rood) |
| **Blauw** | Band 2 (Groen) | Band 3 (Groen) |

</div>

<br>

### 3. Berekening van de NDVI

De Normalized Difference Vegetation Index, of NDVI, meet het groen en de dichtheid van de vegetatie die door het satellietbeeld wordt vastgelegd. De waarde ligt tussen -1 en 1. De formule is als volgt:

De tool die ik op ENVI zal gebruiken heet 'Band Maths'. Het is een tool waarmee een wiskundige bewerking of een aangepaste functie kan worden toegepast op een of meer banden van een beeld. Ik zal deze NDVI-formule toepassen voor elk van mijn beelden. Natuurlijk zijn de banden die voor de NDVI worden gebruikt verschillend tussen satellieten. Dus voor de eerste twee beelden van 1984 en 2011, oftewel beelden van Landsat 5, gebruiken we de volgende formule:

<div class="row justify-content-sm-center" style="text-align: center;">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ndvi_calculation.png" title="NDVI-berekening" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**(Band 4 - Band 3) / (Band 4 + Band 3)**

Voor Landsat 7 gebruiken we de volgende:

**(Band 5 - Band 4) / (Band 5 + Band 4)**

### 4. Tool voor beeldverschil

Dankzij de tool 'Change Detection Workflow' op ENVI is het voor ons gemakkelijk om veranderingen tussen twee data te detecteren. We zullen ons met name concentreren op de optie 'Image Difference', die als concept het over elkaar leggen van het beeld 'na' op het beeld 'voor' heeft en vervolgens een aftrekking van de pixels om de evoluties in de loop van de tijd te kunnen detecteren. De gangbare toepassingen van deze tool zijn: milieumonitoring, zoals ontbossing; stadsontwikkeling, zoals het aantal gebouwen dat aan een commerciële zone is toegevoegd, enz... Wat perfect past in onze studie.

## ANALYSE

### I/ Brasilia, een stad die verdicht

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image1.jpg" title="Beeld 1: Brasilia (1984) in valse kleuren (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 1: Brasilia (1984) in valse kleuren (Linear 2%)
</div>

Het beeld van Brasilia in 1984 in valse kleuren stelt ons in staat de verschillende elementen van onze studiezone te waarderen. In lichtblauw zijn de verstedelijkte gebieden weergegeven en in rood de chlorofylhoudende groene ruimtes. Inderdaad, wat betreft de ruimtelijke structuur van Brasilia, verdeelde Lucio Costa (de stedenbouwkundige achter het plan van deze stad) de bebouwde ruimte in vier sectoren: monumentaal, residentieel, sociaal en bucolisch (zie figuur 1). De architect verbood de vermenging van sectoren niet, maar de verdeling die in Brasilia werd toegepast, leidde tot de verdeling van functies over het hele grondgebied. De theorie van het functionalisme, verdedigd door Le Corbusier, is ongetwijfeld zijn grootste invloed. Bovendien werd in Brasilia de grond gecontroleerd door de staat en administratief verdeeld, in plaats van verkocht op een vrije markt.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig1.jpg" title="Figuur 1: Landgebruik in bebouwd gebied in het Federaal District (2017)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figuur 1: Landgebruik in bebouwd gebied in het Federaal District (2017). Bron: SEGETH, 2017
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image2.jpg" title="Beeld 2: Brasilia (2011) in valse kleuren (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 2: Brasilia (2011) in valse kleuren (Linear 2%)
</div>

Deze kaart (Figuur 1), uit een artikel geschreven door Cayo Costa en Sugie Lee over de stedelijke evolutie van Brasilia, stelt ons in staat de verdeling van het grondgebied in sectoren te identificeren op basis van verschillende functies. We observeren dat het ruimtebeslag voornamelijk is gewijd aan wonen. Op onze satellietbeelden identificeren we ze duidelijk als de dichtste ruimtes. Het is interessant om te zien dat deze woonzones in de loop der jaren blijven verdichten en uitbreiden, terwijl de andere zones "bevroren" blijven.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image3.jpg" title="Beeld 3: Brasilia (2024) in valse kleuren (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 3: Brasilia (2024) in valse kleuren (Linear 2%). <br>
    <b>Groen</b>: Bevroren zone (commercieel en institutioneel). <b>Paars</b>: Zone in constante evolutie (residentieel)
</div>

De onderstaande tabel (Figuur 2) geeft details over de constante toename van de bevolking van Brasilia. Van de jaren 1980 tot 2015 is de bevolking bijna verdubbeld, maar de dichtheid is verrassend genoeg gedaald. Dit doet vermoeden dat Brasilia niet in een logica van verdichting zit, maar eerder van stedelijke uitbreiding. Aangezien de stad de theorie van het functionalisme van Le Corbusier volgt, gebruikt de stad de capaciteiten van auto's om buiten haar grenzen uit te breiden.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig2.jpg" title="Figuur 2: Demografische groei van Brasilia van 1960 tot 2015" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figuur 2: Demografische groei van Brasilia van 1960 tot 2015. Bron: IBGE (Braziliaans Instituut voor Geografie en Statistiek)
</div>

### II/ Een decentralisatie van de stad

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig3.jpg" title="Figuur 3: Stedelijke agglomeratie en economische decentralisatie" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figuur 3: Stedelijke agglomeratie en economische decentralisatie gepromoot door stedelijk ontwikkelingsbeleid tussen eind jaren 1980 en jaren 1990. Bron: Costa, Cayo en Sugi Lee
</div>

De verdichting van de stad Brasilia leidde begin jaren 1980 tot de oprichting van twee nieuwe satellietsteden. Ze begonnen met Samambaia (1981) en vervolgens werd een industriële sector geïnstalleerd (Ceilândia) om te voldoen aan de vraag naar banen in de regio, gevolgd door de aanleg van een snelweg die rechtstreeks verbonden is met Brasilia. In de daaropvolgende jaren richtte de regering van Brasilia, om te reageren op het tekort aan woningen, de administratieve gemeente Samambaia op, en vervolgens Santa Maria, Recanto das Emas, São Sebastião, Paranoá, Riacho Fundo 1 en 2, en Candangolândia.

Met deze informatie wilde ik de verschijning van deze satellietsteden detecteren door een beeldverschil te maken tussen 1984 en 2024. Dit is wat ik heb verkregen:

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image4.jpg" title="Beeld 4: Detectie van satellietsteden via beeldverschil (1984-2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 4: Detectie van satellietsteden via beeldverschil (1984-2024)
</div>

Rechtsboven: Samambaia
Linksboven: Taguatinga
Linksonder: Gama

### III/ Brasilia, een groene stad?

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image5.jpg" title="Beeld 5: NDVI Brasilia (1984)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 5: NDVI Brasilia (1984)
</div>

Behalve zijn futuristische aspect, staat Brasilia ook bekend om zijn natuur. De stad ligt vlakbij het Nationaal Park Brasilia ten noorden van de stad, met een grote oppervlakte van 423,83 km². Rondom Brasilia en satellietsteden bevinden zich gecultiveerde velden.

Men moet weten dat de NDVI niet alle planten detecteert, maar alleen die met chlorofyl. Het hangt dus af van het seizoen. Het beeld van 1984 en 2024 dateert uit mei, terwijl het beeld van 2011 uit september dateert. Helaas heb ik niet dezelfde maanden geselecteerd vanwege het gebrek aan goede beelden op de USGS-site. Echter, volgens deze klimatologische grafiek lijkt het klimaat in Brasilia in mei en september op elkaar. Dus een kruisanalyse kan relevant zijn.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig4.jpg" title="Figuur 4: Gewoonlijk klimaat in Brasilia gedurende het jaar" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figuur 4: Gewoonlijk klimaat in Brasilia gedurende het jaar
</div>

Door de jaren heen merken we dat bepaalde groene ruimtes in Brasilia zijn aangetast: ze verliezen hun chlorofylcapaciteit. Dit is waarneembaar omdat de groene ruimtes die in 1984 helderblauw zijn, een afname van de NDVI hebben gekend op het beeld van 2011 en 2024. Sommige plaatsen die deze afname hebben ondergaan, zijn gekoppeld aan verstedelijking.

Maar over het algemeen heeft Brasilia, ondanks het belang van het bebouwde oppervlak, een relatief belangrijk groen stedelijk oppervlak. Wetende dat het een typische moderne stad is die het gebruik van auto's promoot, probeert de stad groen aan te planten om de ver kunstmatiging te compenseren.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image6.jpg" title="Beeld 6: NDVI Brasilia (2011)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 6: NDVI Brasilia (2011)
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image7.jpg" title="Beeld 7: NDVI Brasilia (2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Beeld 7: NDVI Brasilia (2024)
</div>

## CONCLUSIE

"De bouw van Brasilia maakt deel uit van een bepaalde Braziliaanse verbeelding. Dit proces begon in de jaren 1920 en 1930 en bereikte zijn hoogtepunt in de jaren 1950. Het trachtte, via de centrale overheid, de Braziliaanse natiestaat op te bouwen en tegelijkertijd een nationale identiteit te smeden" (BASSI, 2023)[^1].

Brasilia is een voorbeeld van een stedelijke utopie. Het lijdt momenteel aan tal van sociale en economische verschillen en wordt ook opgeschrikt door corruptieschandalen. Terwijl Brasilia begon met een vooraf bepaald proefplan, beperkt tot 500.000 inwoners; veroorzaakte de sterke immigratie uit het noorden van Brazilië tussen 1957 en 1958 een demografische explosie en werden er nieuwe satellietsteden gecreëerd. Helaas gaat deze uitbreiding gepaard met informele huisvesting en verbergt de stad die futuristisch wil zijn een trieste realiteit.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig5.jpg" title="Figuur 5: Cartografie van de stedelijke evolutie van Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figuur 5: Cartografie van de stedelijke evolutie van Brasilia
</div>

## BIBLIOGRAFIE

[See original French bibliography]

[^1]: Danilo Guiral Bassi...

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
    <h3>Download het volledige artikel</h3>
    <a href="/assets/pdf/M1GAEUR_Rendu_Teledetection_HAZARA_Kalma.pdf" target="_blank" class="btn-zoom">
        <i class="fas fa-file-pdf"></i> Download origineel artikel - PDF
    </a>
</div>
