---
layout: page
title: Certifications
lang: en
key: certifications
translations:
  fr: /fr/certification/
  nl: /nl/certification/
  id: /id/certification/
permalink: /en/certification/
description: My awards, certifications, and diplomas.
nav: true
nav_order: 3
display_categories: [Awards, Certifications, Diplomas]
horizontal: false
---

<div class="projects">
{%- assign lang_items = site.certifications | where: "lang", page.lang -%}

{%- if page.display_categories %}
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_items = lang_items | where: "category", category -%}
  {%- assign sorted_items = categorized_items | sort: "importance" %}
  <div class="grid">
    {%- for project in sorted_items -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {% endfor %}
{%- else -%}
  {%- assign sorted_items = lang_items | sort: "importance" -%}
  <div class="grid">
    {%- for project in sorted_items -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
{%- endif -%}
</div>
