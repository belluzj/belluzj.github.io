---
layout: default
title: Projets
lang: fr
versions:
  en: projects.html
  fr: projets.html
current: "project"
---

Projets
--------

### Scolaires
{:#school}

<ul class="posts">
{% for post in site.categories['projects'] %}
{% if post.categories contains 'school' and post.lang == page.lang %}
<li><span class="margin meta time">{% if post.period %}{{ post.period }}{% else %}{{ post.date | date_to_string }}{% endif %}</span>
<a href="{{ post.url }}">{{ post.title }}</a></li>
{% endif %}
{% endfor %}
</ul>

### Personnels

<ul class="posts">
{% for post in site.categories['projects'] %}
{% unless post.categories contains 'school' or post.lang != page.lang %}
<li><span class="margin meta time">{% if post.period %}{{ post.period }}{% else %}{{ post.date | date_to_string }}{% endif %}</span>
<a href="{{ post.url }}">{{ post.title }}</a></li>
{% endunless %}
{% endfor %}
</ul>
