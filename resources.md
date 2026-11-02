---
layout: page
title: Resources
seo_title: "Official data sources for pharma and digital health in Italy and the EU"
permalink: /resources/
description: "Curated official sources used in the analyses: AIFA, OsMed, ISTAT, ECDC, WHO ATC/DDD, HL7 FHIR, EU AI Act, European Health Data Space (EHDS), GDPR, EMA."
---

<p class="lede-small">The primary sources behind the articles and the PharmaPlanTest prototype. Every figure on this site should be traceable to one of these.</p>

{% for g in site.data.resources %}
<h2 id="{{ g.group | slugify }}">{{ g.group }}</h2>
<ul class="resource-list">
{% for r in g.items %}<li><a href="{{ r.url }}" target="_blank" rel="noopener">{{ r.name }}</a><span>{{ r.note }}</span></li>
{% endfor %}
</ul>
{% endfor %}

See also the [glossary]({{ '/glossary/' | relative_url }}) for definitions of the terms used.
