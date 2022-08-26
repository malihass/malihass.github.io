---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
redirect_from: 
  - "/Publications"
  - "/publications"
  - "/Publications.html"
  - "/publications.html"
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

<h2><i>Journal Articles</i></h2>
{% for post in site.publications reversed %}
  {% if post.pubtype == 'journal' %}
      {% include archive-single-publications.html %}
  {% endif %}
{% endfor %}

<h2><i>Under review</i></h2>
{% for post in site.publications reversed %}
  {% if post.pubtype == 'review' %}
      {% include archive-single-publications.html %}
  {% endif %}
{% endfor %}

<h2><i>Conference Papers</i></h2>
{% for post in site.publications reversed %}
  {% if post.pubtype == 'conference' %}
      {% include archive-single-publications.html %}
  {% endif %}
{% endfor %}

<h2><i>Thesis</i></h2>
{% for post in site.publications reversed %}
  {% if post.pubtype == 'thesis' %}
      {% include archive-single-publications.html %}
  {% endif %}
{% endfor %}

