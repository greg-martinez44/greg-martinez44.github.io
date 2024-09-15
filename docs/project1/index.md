---
title: Project 1
layout: default
has_children: true
nav_order: 4
ticket_name: Collections
---

# Project 1

This is a test project 1.

{% raw %}{{ site.data.mcp.tickets.Collections.link }}{% endraw %}


<!-- <ul>
{% for ticket in site.data.mcp.tickets %}
{% assign org = org_hash[1] %}
  <li>
    <a href="https://github.com/{{ org.username }}">
      {{ org.name }}
    </a>
    ({{ org.members | size }} members)
  </li>
{% endfor %}
</ul> -->