---
layout: home
title: Money Hole
excerpt: "America’s most trusted source for financial enlightenment and deranged scams."
paginate: 12
entries_layout: grid
show_excerpts: true
---

{% comment %}
Hero: latest 3 posts from category 'exclusives' with 'featured: true'
{% endcomment %}
<div class="feature-row">
  {% assign heroes = site.posts | where_exp: "p", "p.categories contains 'exclusives' and p.featured == true" | slice: 0,3 %}
  {% for post in heroes %}
    <article class="feature__item">
      <a class="feature__image" href="{{ post.url | relative_url }}">
        <img src="{{ post.hero | default: post.image | relative_url }}" alt="{{ post.title | escape }}">
      </a>
      <div class="feature__content">
        <h2 class="archive__item-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p class="archive__item-excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</p>
      </div>
    </article>
  {% endfor %}
</div>
