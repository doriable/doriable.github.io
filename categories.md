---
layout: page
title:  "Categories"
permalink: /categories/
order: 1
---

<!--TODO: add a dropdown, on click, of posts in a given category-->

<ul>
{% assign categories_list = site.categories %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %}
      <li>
        <a href="#{{ category | replace:' ','-' }}-ref">
          {{ category | capitalize }}
          <span class="badge pull-right">{{ site.categories[category].size }}</span>
        </a>
      </li>
    {% endfor %}
  {% else %}
    {% for category in categories_list %}
      <li>
        <a href="#{{ category[0] | replace:' ','-' }}-ref">
          {{ category[0] | capitalize }}
          <span class="badge pull-right">{{ category[1].size }}</span>
        </a>
      </li>
  {% endfor %}
  {% endif %}
  {% assign categories_list = nil %}
</ul>
