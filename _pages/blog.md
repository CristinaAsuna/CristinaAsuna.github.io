---
layout: blog
permalink: /blog/
title: "Blog"
---

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
<h2 class="blog-year" id="{{ year }}">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  <article class="blog-card" itemscope itemtype="https://schema.org/CreativeWork">
    <h1 class="blog-card__title" itemprop="headline"><a href="{{ post.url | relative_url }}" rel="permalink">{{ post.title }}</a></h1>
    {% if post.excerpt %}<p class="blog-card__excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 220 }}</p>{% endif %}
    <p class="blog-card__meta">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
      {% if post.categories.size > 0 %}<span aria-hidden="true">·</span> {{ post.categories | join: " · " }}{% endif %}
      {% if post.tags.size > 0 %}<span aria-hidden="true">·</span> {{ post.tags | join: " · " }}{% endif %}
    </p>
  </article>
{% endfor %}
