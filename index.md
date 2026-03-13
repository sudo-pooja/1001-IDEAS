---
layout: home
title: Welcome
---

# My 1000-Day Journey

I'm reading "1000 ideas that changed the way we think".

## Recent Posts

{% for post in site.posts %}
- **{{ post.date | date: "%b %d, %Y" }}** – [{{ post.title }}]({{ post.url | relative_url }})  
  {% if post.categories %} *Category: {{ post.categories | join: ", " }}* {% endif %}
  {% if post.tags %} Tags: {{ post.tags | join: ", " }} {% endif %}
{% endfor %}
