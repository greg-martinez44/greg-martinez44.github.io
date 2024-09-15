---
title: My Homepage
layout: home
date: 2024-09-14
last_modified_date: 2024-09-14
nav_order: 1
---

# My Homepage
{: .no_toc }

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

<ul>
  {% for ticket in site.service_catalog %}
    <li>
      <a href="{{ ticket.url }}">{{ ticket.title }}</a>
      {{ ticket.excerpt }}
    </li>
  {% endfor %}
</ul>
