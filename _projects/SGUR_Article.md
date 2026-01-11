---
layout: page
title: SGUR Article
permalink: /projects/sgur-article/
description: A deep dive into the SGUR project with interactive translation.
img: assets/img/publication_preview.jpg
importance: 3
category: Research
lang: en
---

## Article Presentation

This article explores the implementation of urban resilience strategies. Below you can read the abstract and key sections. Hover over the French text to see the English translation!

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
    background-color: #f8f9fa; /* Light grey background for visibility */
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
    height: 100%;
    opacity: 0;
    background-color: #fff; /* White background for clean text */
    z-index: 10;
    pointer-events: none; /* Let clicks pass through if needed */
    display: flex; /* To align items if needed, or just block */
    align-items: center; /* Vertically center if single block */
}

/* Hover Effect */
.translation-container:hover .text-translated {
    opacity: 1;
}

.translation-container:hover .text-original {
    opacity: 0.2; /* Fade out original slightly or completely */
}

/* Dark Mode Adjustments */
body.dark-theme .text-content {
    background-color: #2c2c2c;
    color: #e0e0e0;
}
body.dark-theme .text-translated {
    background-color: #333;
}
</style>

### Abstract / Résumé

<div class="translation-container">
    <div class="text-content text-original">
        <h4>Version Française</h4>
        <p>
            Ceci est un exemple de paragraphe en français. L'article traite des sujets complexes de l'urbanisme et de la résilience. 
            Le survol de ce texte affichera la version anglaise correspondante, permettant une compréhension rapide pour les lecteurs non francophones.
        </p>
    </div>
    <div class="text-content text-translated">
        <h4>English Version</h4>
        <p>
            This is an example paragraph in French. The article deals with complex topics of urban planning and resilience.
            Hovering over this text will display the corresponding English version, allowing for quick understanding for non-French speaking readers.
        </p>
    </div>
</div>

<div class="translation-container">
    <div class="text-content text-original">
        <p>
            Un deuxième paragraphe pour montrer que l'effet fonctionne sur des blocs multiples. 
            N'hésitez pas à copier-coller votre propre texte ici depuis le PDF.
        </p>
    </div>
    <div class="text-content text-translated">
        <p>
            A second paragraph to show that the effect works on multiple blocks.
            Feel free to copy and paste your own text here from the PDF.
        </p>
    </div>
</div>

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
    background-color: #ad606b !important; /* Pink on hover */
    box-shadow: 0 10px 25px rgba(173, 96, 107, 0.4);
    transform: scale(1.05); 
    color: white !important;
}
</style>

<div style="text-align: center; margin-top: 50px; margin-bottom: 40px;">
    <h3>Download the Full Article</h3>
    <a href="/assets/pdf/SGUR_Hazara_Kalma.pdf" target="_blank" class="btn-zoom">
        <i class="fas fa-file-pdf"></i> Download PDF
    </a>
</div>
