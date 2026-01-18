---
layout: page
title: Pemetaan Kemudahan Berjalan Kaki
permalink: /id/projects/walkability-mapping/
description: Analisis kemudahan berjalan kaki dari kota pilihan Anda menggunakan hanya data terbuka OSM dan alat geospasial.
img: assets/img/walkability_thumbnail.PNG
importance: 1
category: Mapping
lang: id
--- 

## Deskripsi Proyek
Kota-kota senang berbicara tentang kemudahan berjalan kaki (walkability). Namun seberapa mudah sebuah kota dijelajahi dengan berjalan kaki dalam praktiknya ketika mobilitas sehari-hari sangat bergantung pada transportasi umum?
Proyek ini mengeksplorasi pertanyaan tersebut dengan menghasilkan skor spasial kemudahan berjalan kaki berdasarkan akses ke perhentian transportasi umum, menggunakan hanya data terbuka OSM dan alat geospasial.

*Kode ini sangat terinspirasi oleh Afagh Zeydani di Linkedin. Banyak kredit diberikan kepadanya atas karyanya dan karena membagikannya dengan komunitas.*

## Apa yang akan Anda harapkan
- Skor kemudahan berjalan kaki dalam kotak sqm pilihan Anda
- Peta kota dengan skor kemudahan berjalan kaki + perhentian transportasi
- Pembuatan peta folium otomatis

## Cara menggunakannya
Kode saya sangat intuitif. Yang perlu Anda lakukan hanyalah mengubah nama lokasi pilihan Anda di awal kode dan menjalankannya!

*Harap hormati format : "City, Country"*

## Contoh
```python
city = "Amsterdam, Netherlands"
```
## Pustaka yang digunakan
- osmnx
- folium
- geopandas
- shapely
- pandas
- utm
- branca

## Hasil
<iframe src="/assets/html/amsterdam_walkability_map.html" width="100%" height="500px" style="border:none;"></iframe>

## Tertarik menggunakan kembali kodenya?

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
        <i class="fab fa-github"></i> Dapatkan Kode di GitHub
    </a>
</div>
