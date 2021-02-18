---
title: Audits
layout: default
date: 2018-05-30 18:46:00-8:00
---
<h1>Audits</h1>

<h2>Categories</h2>
<ul>
{% for category in site.categories %}
  <li><a href="/blog/category/{{ category | first | replace: ' ', '-' | downcase }}">{{ category | first }}</a> ({{ category[1] | size }})</li>
{% endfor %}
</ul>

<h2>Tags</h2>
<ul>
{% for tag in site.tags %}
  <li><a href="/blog/tag/{{ tag | first | replace: ' ', '-' | downcase }}">{{ tag | first }}</a> ({{ tag[1] | size }})</li>
{% endfor %}
</ul>