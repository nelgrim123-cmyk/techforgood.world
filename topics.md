---
layout: page
title: Topics
seo_title: "Topics: pharmaceutical spending, AI regulation, interoperability, pharma R&D"
permalink: /topics/
description: "All Tech for Good articles grouped by topic: AIFA, OsMed, pharmaceutical spending, AI Act, EHR interoperability, pharma pricing and rebates, AI drug discovery."
---
{%- assign all_tags = "" | split: "" -%}
{%- for p in site.posts -%}{%- assign all_tags = all_tags | concat: p.tags -%}{%- endfor -%}
{%- assign all_tags = all_tags | uniq | sort_natural -%}

<nav class="toc" aria-label="Topics">
{%- for t in all_tags -%}<a href="#{{ t | slugify }}">{{ t }}</a>{%- endfor -%}
</nav>

{% for t in all_tags %}
<h2 id="{{ t | slugify }}">{{ t }}</h2>
<ul class="topic-list">
{% for p in site.posts %}{% if p.tags contains t %}<li><a href="{{ p.url | relative_url }}"{% if p.lang %} hreflang="{{ p.lang }}"{% endif %}>{{ p.title }}</a> <span class="meta">{{ p.date | date: "%b %Y" }}{% if p.lang == 'it' %} · IT{% endif %}</span></li>{% endif %}{% endfor %}
</ul>
{% endfor %}
