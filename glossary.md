---
layout: page
title: Glossary
seo_title: "Pharma & digital health glossary: AIFA, OsMed, ATC, DDD, EHR, FHIR"
permalink: /glossary/
description: "Plain-language glossary of pharma and digital health terms: AIFA, OsMed, ATC, DDD, SSN, AIC, payback, biosimilars, EHR, FHIR, EHDS, AI Act."
---
{%- assign groups = "pharma-italy|Italian pharmaceutical system,regulation|Regulation,data-standards|Data and standards,commercial|Pharma commercial operations,therapies|Therapies and product types" | split: "," -%}

<p class="lede-small">Short definitions of the terms used across the articles. Italian terms keep their original name, with the English meaning alongside.</p>

<nav class="toc" aria-label="Glossary sections">
{%- for g in groups -%}{%- assign gp = g | split: "|" -%}
<a href="#{{ gp[0] }}">{{ gp[1] }}</a>
{%- endfor -%}
</nav>

{% for g in groups %}{% assign gp = g | split: "|" %}
<h2 id="{{ gp[0] }}">{{ gp[1] }}</h2>
<dl class="glossary">
{% assign items = site.data.glossary | where: "group", gp[0] %}
{% for e in items %}
<div class="glossary-item" id="{{ e.term | slugify }}">
<dt>{{ e.term }}{% if e.full %} <span class="glossary-full">{{ e.full }}</span>{% endif %}</dt>
<dd>{{ e.def }}{% if e.link %} <a href="{{ e.link | relative_url }}"{% unless e.link contains '://' %}{% else %} target="_blank" rel="noopener"{% endunless %}>Source &rarr;</a>{% endif %}</dd>
</div>
{% endfor %}
</dl>
{% endfor %}

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "DefinedTermSet",
  "@id": {{ page.url | absolute_url | append: "#glossary" | jsonify }},
  "name": "Tech for Good glossary of pharma and digital health terms",
  "url": {{ page.url | absolute_url | jsonify }},
  "inLanguage": "en",
  "hasDefinedTerm": [
    {%- for e in site.data.glossary %}
    {%- assign slug = e.term | slugify %}
    {
      "@type": "DefinedTerm",
      "name": {{ e.term | jsonify }},
      {%- if e.full %}"alternateName": {{ e.full | jsonify }},{% endif %}
      "description": {{ e.def | jsonify }},
      "url": {{ page.url | absolute_url | append: "#" | append: slug | jsonify }}
    }{% unless forloop.last %},{% endunless %}
    {%- endfor %}
  ]
}
</script>
