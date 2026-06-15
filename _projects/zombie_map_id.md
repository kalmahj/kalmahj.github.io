---
layout: page
title: Pemetaan Risiko Zombifikasi
permalink: /id/projects/zombie-map/
description: Tutorial membuat peta risiko zombifikasi per IRIS di Prancis menggunakan data terbuka OSM dan INSEE.
img: assets/img/zombie_thumbnail.jpg
importance: 2
category: Pemetaan
lang: id
---

## Deskripsi Proyek

Kode ini adalah tutorial tentang cara membuat **peta risiko zombifikasi** yang diskor per IRIS di Prancis.

Semakin tinggi skor, semakin berbahaya IRIS tersebut:
- 🪦 Semakin banyak pemakaman dalam IRIS & semakin dekat dengan pemakaman (×0.35)
- Semakin dekat IRIS dengan bandara (×0.20)
- Semakin tinggi kepadatan penduduk (×0.15)
- Semakin tinggi rasio penduduk berusia 75 tahun ke atas (×0.10)
- Semakin banyak penyandang disabilitas penerima AAH (×0.10)
- Semakin dekat dengan toko senjata (×0.10)

Yang perlu Anda lakukan adalah memasukkan **kode INSEE** dari komune mana saja di Prancis, dan skrip akan secara otomatis menghasilkan peta risiko.

## Dataset yang digunakan

| Dataset | Sumber |
|---|---|
| Titik dan poligon pemakaman | BDTOPO 2026 |
| Kepadatan penduduk | INSEE (basis IRIS 2022) |
| Rasio penduduk 75+ tahun | INSEE (basis IRIS 2022) |
| Penyandang disabilitas (penerima AAH) | CAF / INSEE 2021 |
| Lapangan udara dan bandara | BDTOPO 2026 |
| Toko senjata | OpenStreetMap (OSM) |
| Batas IRIS | IGN CONTOURS-IRIS 2022 |

## Pustaka yang digunakan

- geopandas
- pandas
- numpy
- folium
- branca
- scikit-learn

## Pratinjau Aplikasi

<img src="/assets/img/image_bat.PNG" width="100%" style="border-radius: 8px; margin-bottom: 20px;" alt="Pratinjau aplikasi">

## Hasil

<iframe src="/assets/html/zombie_map.html" width="100%" height="500px" style="border:none; border-radius: 8px;"></iframe>

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
    background-color: #ad606b !important;
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: rotateX(360deg);
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://github.com/kalmahj/zombie-map" target="_blank" class="btn-flip">
        <i class="fab fa-github"></i> Dapatkan Kode di GitHub
    </a>
</div>
