---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

<h2>Pages</h2>
{% assign allowed_pages = "about,cv" | split: "," %}
{% for page in site.pages %}
  {% assign slug = page.url | split: "/" | last %}
  {% if allowed_pages contains slug %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

<h2>Publications</h2>
{% for collection in site.collections %}
  {% if collection.label == "publications" %}
    {% for post in collection.docs %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}

<h2>Talks</h2>
{% for collection in site.collections %}
  {% if collection.label == "talks" %}
    {% for post in collection.docs %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}
