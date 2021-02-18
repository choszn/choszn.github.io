---
layout: views
title: Views
permalink: /Views/
---
<ul><h3>
{% for tag in site.tags %}
<a href="/tag/{{ tag | first | replace: ' ', '-' | downcase }}">{{ tag | first }} |</a>
{% endfor %}
</h3></ul>