---
layout: page
title: Pemodelan Bangunan 3D
permalink: /id/projects/3d-building-modelling/
description: Model bangunan 3D multipatch yang dibuat menggunakan titik LiDar dan alat geoprocessing ArcGIS.
img: assets/img/lidar_thumbnail.PNG
importance: 1
category: Pemetaan
lang: id    
---

## Deskripsi Proyek
Data LiDar adalah alat yang ampuh untuk membuat model objek 3D. Dalam proyek ini, saya menggunakan data LiDar dan alat geoprocessing ArcGIS untuk membuat model 3D multipatch Gulpen, Belanda menggunakan ArcGIS Pro.

## Apa itu data Lidar?
Light Detection and Ranging (lidar) adalah teknologi yang digunakan untuk membuat model elevasi tanah beresolusi tinggi dengan akurasi vertikal 10 sentimeter (4 inci). Peralatan Lidar, yang mencakup pemindai laser, Global Positioning System (GPS), dan Inertial Navigation System (INS), biasanya dipasang di pesawat kecil.

Pemindai laser memancarkan pulsa cahaya singkat ke permukaan tanah. **Pulsa-pulsa tersebut dipantulkan atau disebarkan kembali dan waktu tempuhnya digunakan untuk menghitung jarak antara pemindai laser dan tanah**

Data Lidar awalnya dikumpulkan sebagai "awan titik" (point cloud) dari titik-titik individual yang dipantulkan dari segala sesuatu di permukaan, termasuk struktur dan vegetasi. Untuk menghasilkan Digital Elevation Model (DEM) "bare earth", struktur dan vegetasi dihilangkan (USGS, 2022).

Misalnya, mobil modern menggunakan data LiDar untuk menavigasi melalui kota, atau mendeteksi rintangan tiba-tiba di jalan yang tidak dapat ditangkap oleh kamera biasa.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/lidar.jpg" title="Contoh data Lidar" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Bagaimana cara mendapatkan data Lidar?
Jika Anda berada di AS, Anda dapat mengakses data Lidar dari USGS (US Geological Survey).
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
        Klik di sini untuk mengakses data Lidar AS
    </a>
</div>

Jika Anda berada di Prancis, saya sangat menyarankan Anda menggunakan Lidar 3D oleh IGN (Institut Géographique National). Ini adalah layanan gratis yang disediakan oleh pemerintah Prancis.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://geoservices.ign.fr/lidarhd" target="_blank" class="btn-zoom">
        Klik di sini untuk mengakses data Lidar Prancis
    </a>
</div>

Jika Anda berada di Belanda, saya sangat menyarankan Anda menggunakan Lidar 3D oleh Actueel Hoogstebestand Nederland (AHN). Ini adalah layanan gratis yang disediakan oleh pemerintah Belanda.

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://www.ahn.nl/dataroom" target="_blank" class="btn-zoom">
        Klik di sini untuk mengakses data Lidar Belanda
    </a>
</div>

## Hasil
<video width="100%" controls>
  <source src="/assets/img/3d_arcgis.mp4" type="video/mp4">
  Browser Anda tidak mendukung tag video.
</video>

## Tertarik mengikuti tutorialnya?

<div style="text-align: center; margin-top: 20px; margin-bottom: 40px;">
    <a href="https://learn.arcgis.com/fr/projects/extract-3d-buildings-from-lidar-data/" target="_blank" class="btn-zoom">
        Klik di sini untuk mengakses tutorial
    </a>
</div>
