---
layout: page
title: Documentation
excerpt: Documentation for Traffic Light Replacer - Articles, Getting Started, Main Window, Settings, Pack Creation, Changelog
permalink: /documentation
ref: documentation
order: 0
---
{% for post in site.posts reversed %}
{% if post.category == "documentation" %}
<div class="item">
<h3><a href="{{ post.url }}">
{{ post.title }}
</a></h3>
<p>{{post.description}}</p>
</div>
{% endif %}
{% endfor %}