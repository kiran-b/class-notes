---
layout: default
title: Class Notes
---
## MIT Notes
  <p>
    I'm an MIT EECS '13. I've been putting together my notes from this semester here.
  </p>

### All note categories
- [6.824: Distributed Systems]({{site.siturl}}/pages/6824)
- [21L.011: Intro to Film]({{site.siteurl}}/pages/21L011)
- [Talks I've attended]({{site.siteurl}}/pages/talks)
- [Research Notes]({{site.siteurl}}/pages/UROP)

### Recent notes
{% for post in site.posts limit: 5 %}
- {{ post.date | date_to_string }} &raquo; [{{ post.title }}]({{site.siteurl}}{{ post.url }})
{% endfor %}