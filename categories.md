---
layout: page
title:  "Categories"
permalink: /categories/
order: 1
---

<ul>
{% assign categories_list = site.categories %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %}
      <li>{{ category | capitalize }}, {{ site.categories[category].size }} posts</li>
      <ul>
        {% for post in categories_list.category %}
          <li>{{ post.title }}</li>
        {% endfor %}
      </ul>
      </li>
    {% endfor %}
  {% else %}
    {% for category in categories_list %}
    <li>{{ category[0] | capitalize }}, {{ category[1].size }} posts
      <ul>
        {% for post in category[1] %}
          <li><a href="{{ post.url }}">{{ post.title }}</a>, {{ post.date | date: "%b %-d, %Y" }}</li>
        {% endfor %}
        </ul>
    </li>
  {% endfor %}
  {% endif %}
  {% assign categories_list = nil %}
</ul>
