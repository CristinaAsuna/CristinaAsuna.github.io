---
layout: archive
permalink: /blog/
title: "Blog"
author_profile: true
---

这里记录学习、研究与生活中的一些想法。

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h2 id="{{ year }}-ref">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork">
    <h3 class="archive__item-title" itemprop="headline">
      <a href="{{ post.url | relative_url }}" rel="permalink">{{ post.title }}</a>
    </h3>
    <p class="page__meta"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time></p>
    {% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 180 }}</p>{% endif %}
  </article>
{% endfor %}
