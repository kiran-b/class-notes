---
layout: default
title: Class Notes
---
## MIT Notes
  <p>
    I'm an MIT EECS '13. I've been putting together my notes from this semester here.
  </p>

### All note categories
- [6.824: Distributed Systems]({{site.baseurl}}/pages/distributed-systems)
- [21L.011: Intro to Film]({{site.baseurl}}/pages/21L011)
- [Talks I've attended]({{site.baseurl}}/pages/talks)
- [Research Notes]({{site.baseurl}}/pages/UROP)

### Recent notes
{% for post in site.posts limit: 5 %}
- {{ post.date | date_to_string }} &raquo; [{{ post.title }}]({{site.baseurl}}{{ post.url }})
{% endfor %}