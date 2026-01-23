---
layout: page
title: Melacak Evolusi Perkotaan Brasilia melalui Penginderaan Jauh
permalink: /id/projects/remote_sensing_brazilia/
description: Penggunaan ENVI dan gambar Landsat
img: assets/img/rs_brazilia_fig5.jpg
importance: 1
category: Artikel
lang: id
---

**HAZARA, Kalma**  
Master Geomatika Terapan untuk Studi Perkotaan dan Risiko

**EVOLUSI PERKOTAAN BRASILIA**

**Kursus Master 1 Penginderaan Jauh**

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/title_image_remote_sensing.png" title="Gambar Judul" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## DAFTAR ISI

- [Pendahuluan](#pendahuluan)
- [Metodologi](#metodologi)
  - [Membingkai gambar pada pusat studi saya](#membingkai-gambar-pada-pusat-studi-saya)
  - [Mengatur gambar saya dalam warna palsu](#mengatur-gambar-saya-dalam-warna-palsu)
  - [Perhitungan NDVI](#perhitungan-ndvi)
  - [Alat perbedaan gambar](#alat-perbedaan-gambar)
- [Analisis](#analisis)
  - [Brasilia, kota yang semakin padat](#i-brasilia-kota-yang-semakin-padat)
  - [Desentralisasi kota](#ii-desentralisasi-kota)
  - [Brasilia, kota hijau?](#iii-brasilia-kota-hijau)
- [Kesimpulan](#kesimpulan)
- [Daftar Pustaka](#daftar-pustaka)

## PENDAHULUAN

"Setelah berkemah selama hampir dua ratus tahun di tepi air, Brasil akan mengambil alih wilayahnya." (KUBITSCHEK, 1960). Pada tanggal 21 April 1960, 1200 km dari São Paulo dan Rio de Janeiro, presiden Brasil Juscelino Kubitschek meresmikan ibu kota baru Brasil, bernama Brasilia. Ini adalah contoh perencanaan kota yang unik, karena merupakan kota yang relatif baru yang diciptakan ex nihilo dalam waktu kurang dari tiga tahun, di atas lahan yang belum tersentuh urbanisasi. Dengan keliling 112 km² dan disebut Plano Piloto, kota ini terdaftar sebagai Situs Warisan Dunia UNESCO pada tahun 1987 karena berbagai mahakarya arsitekturnya yang sangat terinspirasi oleh gaya modern. Kota ini memiliki rencana kota sektoral fungsional, memisahkan perumahan, pekerjaan, dan rekreasi dengan populasi yang direncanakan sebesar 500.000 jiwa. Saat ini, Brasilia telah melampaui dua juta penduduk (3,5 juta di wilayah perkotaan), telah menjadi kota metropolis referensi dalam jaringan perkotaan Brasil dan memiliki kepentingan internasional. Pertumbuhan hanya dalam beberapa dekade ini tampak menarik bagi saya untuk deteksi perubahan multi-tanggal. Dengan demikian, berkat perangkat lunak ENVI, saya akan menganalisis 3 gambar satelit Brasilia untuk mengamati perubahan perkotaan yang dialami kota ini.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing1_p2.png" title="Gambar satelit Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/remote_sensing2_p2.png" title="Lokasi" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Gambar diambil dari situs web resmi Survei Geologi Amerika Serikat (USGS Earth Explorer), dari dua satelit Landsat yang berbeda. Berikut adalah tabel yang merinci setiap gambar yang saya gunakan.

<div style="display: flex; justify-content: center;">

|  | TANGGAL AKUISISI | SATELIT |
| :---- | ----- | ----- |
| **GAMBAR 1** | 01/05/1984 | Landsat 5 |
| **GAMBAR 2** | 01/09/2011 | Landsat 5 |
| **GAMBAR 3** | 01/05/2024 | Landsat 7 |

</div>

<br>

## METODOLOGI

Dengan bermain dengan pita spektral dan menggunakan parameter pada ENVI, saya dapat menghasilkan gambar menarik yang akan memungkinkan kita melihat perbedaan perkotaan antara ketiga tanggal tersebut. Mengetahui bahwa ini adalah kota yang cukup unik yang mengikuti rencana yang telah ditentukan sebelumnya, saya akan mencoba menganalisis melalui gambar yang saya peroleh, densifikasi dan perluasan perkotaan Brasilia dari tahun 1980-an hingga hari ini. Berikut adalah metode deteksi yang tampak relevan bagi saya untuk studi ini:

### 1. Membingkai gambar pada pusat studi saya

Di USGS, gambar mentah yang diberikan kepada kita seringkali terlalu besar untuk perimeter studi kita. Oleh karena itu, perlu untuk membingkai gambar pada zona yang menarik bagi saya, yaitu di kota Brasilia dan sekitarnya. Saya menggunakan alat 'Spectral Indice', karena memungkinkan kita untuk meningkatkan skala, tanpa mengurangi resolusi gambar. Proyeksi yang saya gunakan mengikuti logika Amerika: WGS 84.

### 2. Mengatur gambar saya dalam warna palsu

Dalam warna asli, membedakan bangunan dari ruang hijau adalah tantangan. Jadi, dengan bermain dengan pita saluran RGB, saya memilih kombinasi yang memungkinkan visualisasi elemen-elemen yang berbeda dengan lebih jelas: warna palsu. Berikut adalah parameter yang saya gunakan untuk gambar saya berdasarkan jenis satelitnya:

<div style="display: flex; justify-content: center;">

|  | LANDSAT 5 | LANDSAT 7 |
| :---- | ----- | ----- |
| **Merah** | Pita 4 (Inframerah Dekat) | Pita 5 (Inframerah Dekat) |
| **Hijau** | Pita 3 (Merah) | Pita 4 (Merah) |
| **Biru** | Pita 2 (Hijau) | Pita 3 (Hijau) |

</div>

<br>

### 3. Perhitungan NDVI

Normalized Difference Vegetation Index, atau NDVI, mengukur kehijauan dan kepadatan vegetasi yang ditangkap oleh citra satelit. Nilainya berkisar antara -1 dan 1. Rumusnya adalah sebagai berikut:

Alat yang akan saya gunakan di ENVI disebut 'Band Maths'. Ini adalah alat yang memungkinkan penerapan operasi matematika atau fungsi khusus ke satu atau lebih pita gambar. Saya akan menerapkan rumus NDVI ini untuk setiap gambar saya. Tentu saja, pita yang digunakan untuk NDVI berbeda antar satelit. Jadi, untuk dua gambar pertama tahun 1984 dan 2011, yaitu gambar Landsat 5, kita akan menggunakan rumus berikut:

<div class="row justify-content-sm-center" style="text-align: center;">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ndvi_calculation.png" title="Perhitungan NDVI" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**(Pita 4 - Pita 3) / (Pita 4 + Pita 3)**

Untuk Landsat 7, kita akan menggunakan yang berikut:

**(Pita 5 - Pita 4) / (Pita 5 + Pita 4)**

### 4. Alat perbedaan gambar

Berkat alat 'Change Detection Workflow' di ENVI, mudah bagi kita untuk mendeteksi perubahan antara dua tanggal. Kami terutama akan fokus pada opsi 'Image Difference', yang memiliki konsep menumpangkan gambar 'setelah' pada gambar 'sebelum' dan kemudian mengurangi piksel untuk dapat mendeteksi evolusi dari waktu ke waktu. Aplikasi umum alat ini adalah sebagai berikut: pemantauan lingkungan, seperti deforestasi; pengembangan perkotaan, seperti jumlah bangunan yang ditambahkan ke zona komersial, dll... Yang sangat sesuai dengan studi kami.

## ANALISIS

### I/ Brasilia, kota yang semakin padat

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image1.jpg" title="Gambar 1: Brasilia (1984) dalam warna palsu (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 1: Brasilia (1984) dalam warna palsu (Linear 2%)
</div>

Gambar Brasilia tahun 1984 dalam warna palsu memungkinkan kita untuk menghargai berbagai elemen zona studi kita. Biru muda mewakili area urban dan merah adalah ruang hijau berklorofil. Memang, mengenai struktur spasial Brasilia, Lucio Costa (perencana kota di balik rencana kota ini) membagi ruang binaan menjadi empat sektor: monumental, perumahan, sosial, dan bucolic (lihat gambar 1). Arsitek tidak melarang percampuran sektor, tetapi distribusi yang diterapkan di Brasilia menyebabkan sektoralisasi fungsi di seluruh wilayah. Teori fungsionalisme, yang dipertahankan oleh Le Corbusier, tidak diragukan lagi adalah pengaruh terbesarnya. Selain itu, di Brasilia, tanah dikendalikan oleh Negara dan didistribusikan secara administratif, daripada dijual di pasar bebas.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig1.jpg" title="Gambar 1: Penggunaan lahan di area binaan di Distrik Federal (2017)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 1: Penggunaan lahan di area binaan di Distrik Federal (2017). Sumber: SEGETH, 2017
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image2.jpg" title="Gambar 2: Brasilia (2011) dalam warna palsu (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 2: Brasilia (2011) dalam warna palsu (Linear 2%)
</div>

Peta ini (Gambar 1), dari artikel yang ditulis oleh Cayo Costa dan Sugie Lee tentang evolusi perkotaan Brasilia, memungkinkan kita untuk mengidentifikasi sektoralisasi wilayah berdasarkan fungsi yang berbeda. Kami mengamati bahwa jejak tanah sebagian besar didedikasikan untuk perumahan. Pada citra satelit kami, kami mengidentifikasinya dengan jelas sebagai ruang terpadat. Sangat menarik untuk mengamati bahwa zona perumahan ini terus memadat dan berkembang selama bertahun-tahun, sementara zona lainnya tetap "beku".

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image3.jpg" title="Gambar 3: Brasilia (2024) dalam warna palsu (Linear 2%)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 3: Brasilia (2024) dalam warna palsu (Linear 2%). <br>
    <b>Hijau</b>: Zona beku (komersial dan institusional). <b>Ungu</b>: Zona yang terus berkembang (perumahan)
</div>

Tabel di bawah ini (Gambar 2) merinci peningkatan konstan populasi Brasilia. Dari tahun 1980-an hingga 2015, populasinya hampir dua kali lipat, tetapi kepadatannya secara mengejutkan menurun. Ini membawa kita untuk menduga bahwa Brasilia tidak dalam logika densifikasi, tetapi lebih pada perluasan perkotaan. Mengingat bahwa kota ini mengikuti teori fungsionalisme Le Corbusier, kota ini menggunakan kapasitas mobil untuk memperluas melampaui batas-batasnya.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig2.jpg" title="Gambar 2: Pertumbuhan demografis Brasilia dari 1960 hingga 2015" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 2: Pertumbuhan demografis Brasilia dari 1960 hingga 2015. Sumber: IBGE (Institut Geografi dan Statistik Brasil)
</div>

### II/ Desentralisasi kota

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig3.jpg" title="Gambar 3: Aglomerasi perkotaan dan desentralisasi ekonomi" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 3: Aglomerasi perkotaan dan desentralisasi ekonomi yang dipromosikan oleh kebijakan pembangunan perkotaan antara akhir 1980-an dan 1990-an. Sumber: Costa, Cayo, dan Sugi Lee
</div>

Densifikasi kota Brasilia menyebabkan pada awal 1980-an, penciptaan dua kota satelit baru. Mereka dimulai dengan Samambaia (1981) kemudian, sektor industri dipasang (Ceilândia) untuk menanggapi permintaan pekerjaan di wilayah tersebut, diikuti oleh pembangunan jalan tol yang terhubung langsung ke Brasilia. Selama tahun-tahun berikutnya, untuk menanggapi kekurangan perumahan, pemerintah Brasilia mendirikan kotamadya administratif Samambaia, kemudian Santa Maria, Recanto das Emas, São Sebastião, Paranoá, Riacho Fundo 1 dan 2, dan Candangolândia.

Dengan memiliki informasi ini, saya ingin mendeteksi kemunculan kota-kota satelit ini dengan melakukan perbedaan gambar antara 1984 dan 2024. Berikut adalah apa yang saya peroleh:

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image4.jpg" title="Gambar 4: Deteksi kota satelit melalui perbedaan gambar (1984-2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 4: Deteksi kota satelit melalui perbedaan gambar (1984-2024)
</div>

Kanan atas : Samambaia
Kiri atas : Taguatinga
Kiri bawah : Gama

### III/ Brasilia, kota hijau?

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image5.jpg" title="Gambar 5: NDVI Brasilia (1984)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 5: NDVI Brasilia (1984)
</div>

Selain aspek futuristiknya, Brasilia juga dikenal dengan alamnya. Kota ini terletak di dekat Taman Nasional Brasilia di utara kota, yang memiliki area luas 423,83 km². Di sekitar Brasilia dan kota-kota satelit terdapat ladang pertanian.

Harus diketahui bahwa NDVI tidak mendeteksi semua tanaman tetapi hanya yang berklorofil. Jadi, itu tergantung pada musim. Gambar 1984 dan 2024 bertanggal Mei sedangkan gambar 2011 bertanggal September. Sayangnya saya tidak memilih bulan yang sama karena kurangnya gambar yang bagus di situs USGS. Namun, menurut grafik iklim ini, iklim di Brasilia pada bulan Mei dan September serupa. Jadi, analisis silang bisa relevan.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig4.jpg" title="Gambar 4: Iklim biasa di Brasilia dalam setahun" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 4: Iklim biasa di Brasilia dalam setahun
</div>

Selama bertahun-tahun, kami memperhatikan bahwa ruang hijau tertentu di Brasilia telah terdegradasi: mereka kehilangan kapasitas klorofilnya. Ini dapat diamati karena ruang hijau yang berwarna biru cerah pada tahun 1984 mengalami penurunan NDVI pada gambar 2011 dan 2024. Beberapa tempat yang mengalami penurunan ini terkait dengan urbanisasi.

Tetapi secara umum, Brasilia, meskipun pentingnya permukaan binaan, memiliki area hijau perkotaan yang relatif penting. Mengetahui bahwa ini adalah kota modern khas yang mempromosikan penggunaan mobil, kota ini berusaha menanam tanaman hijau untuk mengimbangi artifisialisasi.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image6.jpg" title="Gambar 6: NDVI Brasilia (2011)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 6: NDVI Brasilia (2011)
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_image7.jpg" title="Gambar 7: NDVI Brasilia (2024)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 7: NDVI Brasilia (2024)
</div>

## KESIMPULAN

“Pembangunan Brasilia adalah bagian dari imajiner Brasil tertentu. Proses ini dimulai pada 1920-an dan 1930-an, memuncak pada 1950-an. Itu berusaha membangun, melalui pemerintah pusat, negara-bangsa Brasil dan, pada saat yang sama, untuk menempa identitas nasional” (BASSI, 2023)[^1].

Brasilia adalah contoh kasus utopia perkotaan. Saat ini menderita banyak kesenjangan sosial dan ekonomi dan juga diguncang oleh skandal korupsi. Sementara Brasilia dimulai dengan rencana percontohan yang telah ditentukan sebelumnya, terbatas pada 500.000 penduduk; imigrasi yang kuat dari Brasil utara antara 1957 dan 1958, menyebabkan ledakan demografis dan kota-kota satelit baru diciptakan. Sayangnya, perluasan ini disertai dengan pemukiman informal, dan kota yang ingin menjadi futuristik menyembunyikan kenyataan yang menyedihkan.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/rs_brazilia_fig5.jpg" title="Gambar 5: Kartografi evolusi perkotaan Brasilia" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 5: Kartografi evolusi perkotaan Brasilia
</div>

## DAFTAR PUSTAKA

[See original French bibliography as names/titles are typically cited in original language or standard citation format]

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
    <h3>Unduh Artikel Lengkap</h3>
    <a href="/assets/pdf/M1GAEUR_Rendu_Teledetection_HAZARA_Kalma.pdf" target="_blank" class="btn-zoom">
        <i class="fas fa-file-pdf"></i> Unduh Artikel Asli - PDF
    </a>
</div>
