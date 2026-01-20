---
layout: page
title: Certificeringen
lang: nl
key: certifications
translations:
  en: /en/certification/
  fr: /fr/certification/
  id: /id/certification/
permalink: /nl/certification/
description: Mijn onderscheidingen, certificeringen en prestaties.
nav: true
nav_order: 3
display_categories: [Prijzen, Certificaten, Prestaties]
horizontal: false
---

<div class="projects">
{%- assign lang_items = site.certifications | where: "lang", page.lang -%}

{%- if page.display_categories %}
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_items = lang_items | where: "category", category -%}
  {%- assign sorted_items = categorized_items | sort: "importance" %}
  <div class="certification-list mb-5">
    {%- for project in sorted_items -%}
      {% include certifications.html %}
    {%- endfor %}
  </div>
  {% endfor %}
{%- else -%}
  {%- assign sorted_items = lang_items | sort: "importance" -%}
  <div class="certification-list mb-5">
    {%- for project in sorted_items -%}
      {% include certifications.html %}
    {%- endfor %}
  </div>
{%- endif -%}
</div>
