---
layout: archive
title: ""
permalink: /publications/
author_profile: true
redirect_from: 
  - "/Publications"
  - "/publications"
  - "/Publications.html"
  - "/publications.html"
---

I try to make sure all my publications are freely accessible. If you cannot access one, shoot me a message! (malik[dot]hassanaly[at]gmail[dot]com)

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

<h2><i>Conference</i></h2>
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

