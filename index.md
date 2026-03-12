---
layout: home
title: Welcome
---

# My 1000-Day Journey

I'm reading "1000 ideas that changed the way we think" and writing a reflection every day.

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) – {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
