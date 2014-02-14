---
layout: default
title: Projects
current: "project"
---

Projects
--------

### School projects
{:#school}

<ul class="posts">
{% for post in site.categories['projects'] %}
{% if post.categories contains 'school' %}
<li><span class="margin meta time">{% if post.period %}{{ post.period }}{% else %}{{ post.date | date_to_string }}{% endif %}</span>
<a href="{{ post.url }}">{{ post.title }}</a></li>
{% endif %}
{% endfor %}
</ul>

### Autonomous works

<ul class="posts">
{% for post in site.categories['projects'] %}
{% unless post.categories contains 'school' %}
<li><span class="margin meta time">{% if post.period %}{{ post.period }}{% else %}{{ post.date | date_to_string }}{% endif %}</span>
<a href="{{ post.url }}">{{ post.title }}</a></li>
{% endunless %}
{% endfor %}
</ul>
