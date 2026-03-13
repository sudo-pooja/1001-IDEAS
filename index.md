---
layout: default
title: Welcome
---

<section class="landing-hero">
  <p class="kicker">1000 Days · 1000 Reflections</p>
  <h1>1000 Ideas That Changed The Way I Think</h1>
  <p class="lead">One idea each day from a remarkable book, with one personal reflection that connects it to modern life.</p>
  <div class="hero-actions">
    <a class="button-primary" href="#latest-entries">Start Reading</a>
    <a class="button-ghost" href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a>
  </div>
</section>

<section id="latest-entries" class="entries-section">
  <div class="section-head">
    <h2>Latest Entries</h2>
    <p>Newest posts first, with short previews so you can quickly pick what to read next.</p>
  </div>

  {% assign listing_posts = paginator.posts | default: site.posts %}
  <div class="entries-grid">
    {% for post in listing_posts %}
      <article class="entry-card">
        <p class="entry-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d, %Y" }}</time>
          {% if post.categories and post.categories.size > 0 %}
            <span>· {{ post.categories | first }}</span>
          {% endif %}
        </p>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.excerpt | strip_html | truncate: 170 }}</p>
        <a class="entry-link" href="{{ post.url | relative_url }}">Read Entry</a>
      </article>
    {% endfor %}
  </div>

  {% if paginator and paginator.total_pages > 1 %}
    <nav class="pagination-nav" aria-label="Post pages">
      {% if paginator.previous_page %}
        <a class="page-btn" href="{{ paginator.previous_page_path | relative_url }}">Newer</a>
      {% else %}
        <span class="page-btn disabled">Newer</span>
      {% endif %}

      <p class="page-status">Page {{ paginator.page }} of {{ paginator.total_pages }}</p>

      {% if paginator.next_page %}
        <a class="page-btn" href="{{ paginator.next_page_path | relative_url }}">Older</a>
      {% else %}
        <span class="page-btn disabled">Older</span>
      {% endif %}
    </nav>
  {% endif %}
</section>
