---
layout: article
title: News
---


{% assign groups = site.posts | group_by_exp: "p", "p.date | date: '%Y'" %}
{% for year in groups %}
  <h2>{{ year.name }}</h2>
  <ul>
  {% for post in year.items %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span>{{ post.date | date: "%b %d, %Y" }}</span>
    </li>
  {% endfor %}
  </ul>
{% endfor %}
