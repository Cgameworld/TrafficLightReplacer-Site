---
layout: post
title: Changelog
category: documentation
---

Commit by commit changelog: [GitHub master branch](https://github.com/Cgameworld/TrafficLightReplacer/commits/master)
<br><br>

Changelog for all of the public releases of the mod:

  <ul class="post-list">
    {% for post in site.posts %}
    {% if post.category == "changelog" %}
      <li>

        {% assign date_format = site.cayman-blog.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | absolute_url }}" title="{{ post.title }}">{{ post.title | escape }}</a>
        </h2>

        {{ post.excerpt | markdownify | truncatewords: 30 }}

      </li>
      {% endif %}
    {% endfor %}
  </ul>
