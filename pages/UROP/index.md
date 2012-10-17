---
layout: default
title: Summary | Research
---
## Research

  <p>
    Notes from research-related meetings.
  </p>

### All classes:

  <ul class="posts">
    {% for post in site.categories.UROP %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{site.siteurl}}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>