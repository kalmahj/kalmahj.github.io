---
layout: page
title: GIS Pemilu selama Pemilu Eropa 2024
permalink: /id/projects/electory_gis/
description: Mengungkap realitas elektoral melalui pemetaan selama Pemilu Eropa 2024
img: assets/img/electory_gis.jpg
importance: 1
category: Mapping
lang: id
---

## Konteks
Pemilu Eropa 2024 adalah momen penting bagi demokrasi di Eropa. Partai Sayap Kanan mendapatkan momentum dan penting untuk memahami apa yang sebenarnya dikatakan statistik.

Berikut adalah peta hasil pemilu untuk Partai Sayap Kanan selama Pemilu Eropa 2024, mengungkapkan realitas politik tertentu yang biasanya tidak ditampilkan oleh peta di berita. 

Di bawah ini Anda dapat membaca analisis infografis lengkap dengan terjemahan interaktif. **Arahkan kursor ke teks bahasa Prancis untuk melihat versi bahasa Indonesia!**

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

## Data & alat yang digunakan
- Set Data Pemilu Eropa 2024 dari Pemerintah Prancis

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.data.gouv.fr/pages/donnees-des-elections" target="_blank" class="btn-zoom">
        Klik di sini untuk mengakses Set Data Pemilu Eropa 2024
    </a>
</div>

- QGIS untuk Pemetaan
- Inkscape untuk sentuhan estetika

## Analisis Infografis

<div class="row mt-5">
    <div class="col-md-7">
        {% include figure.html path="assets/img/electory_gis.jpg" title="Infografis analisis elektoral" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-5">
        <div class="translation-container">
            <div class="text-content text-original">
                <h4>Le Rassemblement National était-il vraiment en tête des élections ?</h4>
                <p>Une carte de Nicolas Lambert et Françoise Bahoken a témoigné une victoire exagérée du RN lors des élections européenes. Beaucoup se demande de la fiabilité de leur carte, à l'égard du manque d'informations statistiques. Ainsi, à partir des bases de données officielles (data.gouv), nous allons tenter de démontrer une cartographie électorale plus réaliste.</p>
            </div>
            <div class="text-content text-translated">
                <h4>Apakah National Rally benar-benar memimpin pemilu?</h4>
                <p>Sebuah peta oleh Nicolas Lambert dan Françoise Bahoken menunjukkan kemenangan yang berlebihan dari RN selama pemilu Eropa. Banyak yang mempertanyakan keandalan peta mereka, mengingat kurangnya informasi statistik. Jadi, menggunakan basis data resmi (data.gouv), kami akan mencoba mendemonstrasikan kartografi elektoral yang lebih realistis.</p>
            </div>
        </div>

        <div class="translation-container">
            <div class="text-content text-original">
                <p><strong>Légende 1 :</strong> Nombre de votes RN</p>
                <p><strong>Légende 2 :</strong> % de votes RN</p>
            </div>
            <div class="text-content text-translated">
                <p><strong>Legenda 1:</strong> Jumlah suara RN</p>
                <p><strong>Legenda 2:</strong> % suara RN</p>
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
                <h4>Analisis</h4>
                <p>Persentase tinggi di kota-kota kecil, di mana bobot demografisnya rendah!</p>
                <p>Hanya 74 kanton dari 1906 yang memiliki mayoritas absolut suara RN.</p>
                <p>Banyak abstain. Nilai maksimum pangsa suara yang diberikan tidak melebihi 65%!</p>
            </div>
        </div>
    </div>
</div>

## Temuan Utama

Analisis ini mengungkapkan nuansa penting dalam interpretasi elektoral:

1. **Konteks Demografis**: Persentase RN tertinggi muncul di daerah dengan bobot demografis rendah
2. **Mayoritas Absolut Terbatas**: Hanya 74 dari 1906 kanton yang menunjukkan mayoritas absolut RN
3. **Tingkat Abstain Tinggi**: Pangsa maksimum suara yang diberikan tetap di bawah 65%

Hal ini menunjukkan pentingnya mengontekstualisasikan peta elektoral dengan informasi statistik yang tepat untuk menghindari representasi yang menyesatkan dari realitas elektoral.
